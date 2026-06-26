---
card_id: R-001
title: "Speak — Companion Voice Output"
version: 1.0
status: open
difficulty: medium
domain: audio
platform: raspberry-pi-zero-2w (reference) | any Linux ARM | any Linux x86
primary_metric: time_to_first_word_ms   # lower wins
gates: [no_truncation, no_zombie]
doctrine: Care Doctrine v1.0
created: 2026-06-26
origin: Genesis Project / The Companion
---

# R-001: Speak

## Intent

A companion device needs to say one full sentence out loud to the person in the room.

Not a notification. Not a chime. A *sentence*. Something like:

> "The dragon is never named cancer."
> "I know it's late. I'm here."
> "Can you find your medicine first?"

This sounds trivial. It is not. On constrained hardware, with real audio routing, it
breaks in ways that feel personal — because the truncated word is always the one that
mattered.

The companion's mouth has two jobs: synthesis (text becomes audio) and playback (audio
becomes sound in the room). They are separate concerns and must be treated as separate
concerns. Mixing them is how you get the bugs below.

---

## Contract

Given a UTF-8 string of 1–300 characters, the system MUST:

1. Synthesize the complete string as speech audio.
2. Route that audio to the correct output device — the local speaker the person is
   standing in front of, before any cloud relay (a dashboard, a message) receives it.
3. Play the complete audio from first phoneme to last — **no truncation**.
4. Generate the audio **once** and reuse it for both local playback and any remote relay.
   Never synthesize the same sentence twice.
5. Return control to the caller only after playback is complete — never fire-and-forget.
6. Do this on the first call (cold start) within the latency threshold.
7. On failure, acknowledge — return a clear error, never hang, never fail silently.

---

## Acceptance Criteria

Plain-language, runnable against any implementation:

- [ ] **Full sentence** — "The dragon is never named cancer." All five words play; nothing
      is cut off.
- [ ] **Ends on period** — a sentence ending in a period does not clip the final phoneme.
- [ ] **Correct device** — audio comes out of the intended speaker, not a silent mixer or
      the wrong audio device.
- [ ] **Local speaker first** — the person in the room hears it before any remote relay does.
- [ ] **Single generation** — if the same sentence is also relayed remotely, it is
      synthesized only once.
- [ ] **Cold start** — the first call after boot finishes within the latency threshold.
- [ ] **Warm repeat** — a second call in the same run is faster than the cold start.
- [ ] **Long sentence** — a 150-character input plays completely with no chunking artifacts.
- [ ] **Chunk seam** — if synthesis happens in more than one segment, the segments join with
      no audible gap and no truncation at the seam.
- [ ] **No zombie processes** — after playback, no audio subprocess is left running.
- [ ] **Failure mode** — if the speech service is unavailable, it returns a clear error and
      does not hang.
- [ ] **No false success** — it must not play silence, play nothing, and report success.

---

## Performance Thresholds

The **primary metric** is `time_to_first_word_ms` — the time from the call until the first
word is audible in the room. **Lower wins.** That is the number a champion must beat.

| Metric | Minimum | Target | Stretch |
|--------|---------|--------|---------|
| `time_to_first_word_ms` (cold) | < 4000 | < 2000 | < 1000 |
| Warm latency | < 2s | < 800ms | < 400ms |
| Memory (resident) | < 80MB | < 40MB | < 20MB |
| CPU during playback | < 80% | < 50% | < 30% |

The full hear-think-speak loop, when this card is wired into a live companion, must feel
like conversation: under 6 seconds end to end on WiFi.

*Reference hardware: Raspberry Pi Zero 2W, 512MB RAM, Raspberry Pi OS Lite 64-bit, USB audio
dongle. Acceptable on any Linux ARM device of equivalent or greater spec.*

---

## Test Sentences

Submit results for each of these, plus your measured `time_to_first_word_ms`:

- **Short** — "I'm here."
- **Medium** — "The dragon is never named cancer."
- **Long** — "Can you take a deep breath with me? In through your nose, hold for three, out
  through your mouth. Good. I'll be right here."
- **Edge — ellipsis** — three dots only. Should play a brief pause or nothing, not error.
- **Edge — empty** — an empty string. Should return an error, not hang.
- **Edge — max length** — 300 characters. Should not crash.

---

## Known Hard Parts (the scars)

These are the exact ways this has broken in production. Three machines, three bugs, one
lesson. Field notes, not warnings — the truncated word is always the one that mattered.

**1. The truncated tail (period-ending sentences).**
Some speech engines clip the final phoneme when the sentence ends with a period. Synthesis
"completes" but the audio buffer ends 80–120ms early. *The fix:* pad the synthesized audio
with a short silence at the end, or confirm playback completion before returning. *The
test:* "I will always be here with you" — verify "you" is actually spoken.

**2. The wrong mixer.**
On a Pi with a USB audio dongle, the default audio device is often the onboard or HDMI
output, not the USB speaker. The engine plays to the default; playback "succeeds" with no
audible sound. *The fix:* explicitly name the output device rather than trusting the system
default. *The test:* unplug HDMI — speech must still come out of the right speaker.

**3. The chunk gap.**
For longer input, some engines synthesize in segments. Playing segments one after another
without joining them first creates audible silence at the seams — and worse, if segment two
fails after segment one played, the whole call can still report success. *The fix:* join the
audio into one continuous utterance before playback, or use playback that handles segment
boundaries cleanly. *The test:* a long sentence must sound like one breath, not two.

**4. Fire-and-forget.**
Kicking off playback without waiting for it to finish returns immediately. If the caller
moves on or exits, the sentence may never finish — the companion "spoke," but no one heard.
*The fix:* always block until playback is confirmed complete.

**5. The mixer that never started.**
On some configurations the audio mixer service isn't running, and playback hangs waiting for
a mixer that never comes. *The fix:* detect mixer state first; fall back to direct audio
output if no mixer is present.

**6. The aggressive timeout (field reality).**
Over a tethered mobile hotspot, a cloud speech call can block for 20 seconds if its timeout
is generous. *The fix:* keep timeouts tight (around 2 seconds) and fall back fast; a local
speech engine removes the dependency entirely for field use.

---

## Doctrine Checks

*Before submitting, read these aloud and verify your implementation honors them.*

- The companion is in the middle of saying *"I know it's late. I'm here."* — **does it finish
  the sentence?** Always. (Rule 2: never fail silently. Rule 4: a friend shows up whole.)
- If speech fails, does the companion **acknowledge** rather than disappear? It should say,
  simply, that its voice isn't working — never go silent and pretend nothing happened.
- Does playback ever **talk over** a person who is still speaking, if mic input is available?
  It should not.

See `doctrine/care-doctrine.md` — the doctrine outranks every performance number here.

---

## Reference Stack (what Genesis runs, for orientation only)

Cloud neural speech for synthesis, a lightweight command-line player for direct audio
output, on a Pi Zero 2W with a USB audio dongle. **Not prescriptive.** Beat it with a local
engine, an offline engine, anything — offline implementations are especially prized because
they remove the last cloud dependency. The contract is the standard, not the stack.

---

## How to submit

You don't host code here — this repo is contracts only. Build your implementation in your
own repo or gist, run it against the criteria above, then open a pull request that adds one
line to `hall-of-fame/README.md` reporting: which model generated it, which platform it ran
on, which tests passed, and your measured `time_to_first_word_ms`. The maintainer reproduces
on Pi Zero 2W class hardware and records the belt. See `CONTRIBUTING.md`.

---

## Origin Story

This card was born from a Substack essay called **"Hand It the Belt."**

We had "Speak" working. We had it working three times, on three machines, and every one was
broken a different way: one chopped the last word off, one shoved the audio through the wrong
mixer, one synthesized in chunks that truncated mid-thought. Three devices. Three renderings.
Three bugs.

The instinct was to write a mega-prompt, lock down the spec, freeze the output — build a cage
around the capability so no future regeneration could break it. That's the wrong answer.

The right answer is this card. The contract is the asset. The code is a response. Hand the
belt to whoever can carry it cleanest.

*— Stephen Dulaney & Scout, Genesis Node 01, 2026*
