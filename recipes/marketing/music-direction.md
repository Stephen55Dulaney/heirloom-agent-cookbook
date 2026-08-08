# Recipe: The House Band (Music Direction)

> The sound of the brand in fifteen seconds. Not notes on a page — a brief tight enough
> for an AI music tool to score a reel you could actually ship.

## What you're cooking

Your reel needs a soundtrack, and "make it feel warm" won't get you one. Music is the
fastest way to set a mood and the easiest thing to get wrong — the wrong genre, the wrong
tempo, or a track so busy it fights the voiceover for room.

This recipe produces a **music brief** — the sonic identity of a 15-second reel, defined
the way a music supervisor would hand it to a composer: genre, instrumentation, tempo, the
rise and fall of energy, reference tracks, and a final tight prompt string ready to paste
into an AI music tool (Suno, Udio, or Stable Audio — software that generates original
music from a text description). You're not writing melodies; you're giving the tool the
structure and vocabulary to generate something a brand could license and ship.

Paste this card into Claude Code or Codex with your brand and your reel, and say "score my
reel." You'll get a genre call, an instrument list, a tempo and energy arc, reference
songs, mood words, a paste-ready prompt, and notes on how the music shares space with the
voice.

## Before you start

The AI should gather context before writing the brief:

- **The Mother Stock** — read `recipes/marketing/product-marketing-context.md` if it
  exists: brand voice, tone, and especially the brand **archetype** (a Sage brand wants
  something contemplative; a Jester brand wants playful, light percussion).
- **The Plating Guide** — read the creative brief at `recipes/marketing/creative-brief.md`
  if it exists, for the personality summary and mood board.
- **The storyboard** from The Sizzle Reel, if it exists — so the music's peak lines up
  with the scene cuts.
- **The voiceover script** from The Table Read, if it exists — so the music carves out
  space for the voice.
- Only then ask for anything missing. Don't re-ask what the documents cover.

## The method

Everything triangulates toward one load-bearing line: the **Suno-ready prompt string**.
Build to it in order.

**Genre and subgenre** — one line, specific. Not "indie" but "lo-fi indie folk with
hip-hop drums." A two-or-three-word subgenre, optionally with a "meets" pairing.

**Instrumentation** — three to six bullets, roughly loudest to quietest: the lead element
("fingerpicked nylon guitar"), the rhythmic foundation ("muted upright bass and brushed
snare"), atmosphere or pads, an optional flourish ("a single bowed cello swell near the
end"), and what to *avoid* ("no big drums, no synth leads, no orchestral strings").

**Tempo and energy arc** — give a tight **5-BPM window** (BPM is beats per minute, the
speed of the track — for example "84–88 BPM"), and resist going over 100 unless the brand
earns it. Use 4/4 time unless there's a strong reason not to. Then describe the energy as a
three- or four-beat sequence across the fifteen seconds: sparse and breath-held on a single
instrument at the open; drums entering and harmony filling in through the middle; a peak
with full instrumentation at the brand moment around 10–13 seconds; then a pull back to
atmosphere with the last note ringing out.

**Reference tracks** — three to five real songs, each with the one dimension it matches:
"Holocene — Bon Iver — the breath-held opening"; "Dreams — Fleetwood Mac — the drum
entrance and pace." These let any tool or supervisor triangulate the target.

**Mood adjective stack** — five to seven single sensory words: warm, unhurried, golden,
wood-grained, nostalgic-not-sad, breathing. Avoid corporate words like "uplifting" or
"dynamic."

**The Suno-ready prompt string** — a single line, max 200 characters, in the order the
tool expects: genre, then BPM, then three or four instruments, then two or three mood
adjectives, then a structure note. As quoted prose it reads like: *lo-fi indie folk, 86
BPM, fingerpicked nylon guitar, brushed drums, Rhodes pad, warm and unhurried, builds at
0:08.* Read it aloud to check it scans; this is the literal text to paste into the tool.

**Audio–voiceover layering note** — one or two lines on how music meets the voice: does it
duck under the voiceover automatically, or do they share frequency space cleanly? Is there
a moment where music drops out for the brand line? What are the final two seconds — full
music with the brand mark, or breath?

**Mix notes** — three or four quick technical touches: loudness (a target around -16 LUFS
sits soft enough for social autoplay, full enough for headphones), stereo field (wide pads,
mono-center rhythm and lead), reverb character (short plate on the lead, no big halls), and
the final half-second (a clean cut or a ring-out).

Remember fifteen seconds is short: you get about one transition, one dynamic move, one
peak. Plan for that — don't describe a four-minute song.

## Acceptance Criteria (how you know it worked)

- [ ] The Suno-ready prompt string is one line, under 200 characters, in the expected order.
- [ ] The tempo is given as a 5-BPM window, and the energy arc is a 3–4 beat sequence.
- [ ] Instrumentation lists the lead first and names what to avoid.
- [ ] Three to five real reference tracks each name the dimension they match.
- [ ] The mood stack is 5–7 sensory single words, no corporate adjectives.
- [ ] The layering note says how the music shares space with the voiceover.

## Primary metric

`paste_and_ship` — pasted straight into the music tool, does the prompt string generate a
track that fits the reel and could be licensed and shipped, with no melody hand-holding?
Yes wins.

## The bright lines (never cross)

- **Instrumental by default.** No vocal music unless explicitly justified — voiced music
  fights the voiceover.
- **Don't overspecify melody.** Stay at the genre, instrumentation, and mood layer; that's
  what these tools do well.
- **Match the brand archetype** pulled from the brief — contemplative for a Sage, playful
  for a Jester.
- **Plan for fifteen seconds:** one transition, one dynamic move, one peak. Not a full song.
- **License-clean.** No proprietary samples, copyrighted melodies, or signature-artist
  sounds you can't recreate — evoke the world, not the exact track.

---

*Music is the mood before anyone knows why. Hand the tool a genre, a tempo, and a feeling
instead of a melody — and fifteen seconds gets a soundtrack the brand can call its own.*
