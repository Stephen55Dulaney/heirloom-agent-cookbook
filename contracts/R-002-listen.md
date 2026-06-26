---
id: R-002
capability: responsive-listening
one_line: Close the listen window promptly when the person stops talking — but never cut off someone still finding a word.
primary_metric: time_to_silence_close_ms
direction: lower-wins
gates: [closes_on_silence, survives_clicks, allows_word_pause]
status: champion held — vad-decide-close, 1500 ms (Day 112). The incumbent 8000 ms fixed window was beaten 5.3×.
---

# R-002 — Responsive Listening

## Intent
When the person finishes speaking, the companion stops listening **promptly** — within a short, *silence-decided* window. It does **not** record for a fixed number of seconds regardless of when they stop, and it does **not** run on forever. But — and this is the heart of it — it **never cuts off someone who is still working to find a word.** The window is closed by *true* silence, tuned for the person it serves.

## Acceptance Criteria (runnable)
- **AC-1 — closes on silence, not on a clock.** Speak a 2-second utterance, then go quiet. The recording ends within the silence threshold of when you stopped — *not* at a fixed 8s or 60s window. *Test: recording_length ≈ speech_length + threshold, never a constant.*
- **AC-2 — the threshold is care-tuned.** A brief mid-utterance pause (~1s, someone thinking) does **not** end the turn; a sustained silence (~1.5s) does. *Test: inject a 1s gap mid-utterance → turn continues; a 1.5s+ trailing silence → turn closes.*
- **AC-3 — clicks and noise don't hold it open.** Speaker or keyboard clicks during silence do not keep the window open. *Test: utterance → clicks → silence still closes (the RMS gate + a sustained-speech requirement reject transient frames).*
- **AC-4 — a max cap backstops it.** The window never runs past MAX_UTTERANCE (e.g. 60s) even if silence is never detected.
- **AC-5 — the live loop IS the silence-detecting path.** The running conversation loop uses the VAD recorder, not a fixed-duration window. *Test: a 2s utterance does not produce a constant 8s recording.*

## Performance Thresholds
- **Primary:** `time_to_silence_close_ms` (lower wins) — ms from true speech-end to window-close.
- **🥇 Champion (held since Day 112, 2026-06-26):** **1,500 ms** — `vad-decide-close`, a pure `decide_close()` decision function. Passes all three gates. *Built by Mojo (opencode/Sonnet), independently verified on a different machine (the Mac re-ran the tests). 6/6 tests pass.*
- **Incumbent it beat:** **~8,000 ms — a *fixed* window.** A `/conversation` turn recorded a constant **8.1s** regardless of when the speaker stopped. The champion beats it **5.3×** while still honoring the word-finding pause.
- **The contest is open:** beat 1,500 ms *without* tripping `allows_word_pause`, and the belt is yours.

## Known Hard Parts (the scars)
- **The good code already exists — it just isn't wired.** The silence-detecting recorder (VAD + `SILENCE_TIMEOUT 1.1s` + RMS gate + clicks-robust counting) lives in `conversation_mode.py`, but the live loop calls a *fixed-duration* recorder instead. **The fix is wiring, not new detection.**
- **Clicks read above the noise floor** and fool naive silence detection. Need an **RMS gate** (sub-floor energy = silence even if the VAD disagrees) **plus a sustained-speech requirement** (a lone click frame is neutral; only ~2+ consecutive speech frames reset the silence count).
- **The mic noise floor fools `webrtcvad`** into "always hearing speech" — the RMS gate is the backstop.
- **A jammed/held push-to-talk button** can override silence detection entirely (records to the 60s cap). The listen path must **not** depend on a physical button's state.

## Doctrine Checks — Care Doctrine, Rule 1 (Patience with Silence)
This contract is **gated by dignity, not just speed.** For a person with a progressive communication illness, *the pause is her — still working — not a gap.*
- A build that closes in 200 ms **FAILS the doctrine** (it cuts her off) even though it wins the latency metric.
- So speed is **bounded**: the floor is ~1s (let her find the word), the ceiling is ~1.5–2s (stay responsive, don't feel like eavesdropping).
- `allows_word_pause` is a **hard gate**: no submission passes by being faster if it cuts off a thinking pause.

> *"I don't fill the pause. When the word is stuck, I wait — because she's still there, still working. The pause is her, not a gap."* — the companion, in the field. This card exists to make that true in *milliseconds.*
