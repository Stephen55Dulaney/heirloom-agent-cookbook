# Recipe: Motion On Your Words

### Animated B-roll where every change lands on something you said

**Status: technique documented, not yet cooked in this kitchen.** This card describes a method we
studied and plan to run on our next walkthrough. When we have, the scars below get real entries and the
numbers get measured. Until then, treat the targets as goals, not results.

Credit: this technique comes from **Bart Slodyczka's `motion-broll` skill**
([github.com/Barty-Bart/motion-graphics](https://github.com/Barty-Bart/motion-graphics), MIT license). If
you want a working engine, start from his. This card says what any engine must do, in our words.

---

## What you're building

Short animated clips that sit on top of (or beside) a talking-head video. The signature is **one shape
that never cuts**: it grows, changes its corners and colour, and swaps what's inside it with a quick blur,
moving from state to state. A cursor seems to drive it, clicking and dragging. **Every change is timed to
a word the narrator says.**

It turns a still slide ("here are the three weights") into a moment ("*three* weights" and the card splits
into three).

---

## The contract

Given a cut video and a transcript with a time for every word, the pipeline MUST:

1. **Make every frame a pure function of time.** Whatever draws frame 312 must draw the same frame 312
   every time, with no leftover state and no timers. That's what makes rendering repeatable and
   frame-by-frame motion blur possible.
2. **Move with springs, not straight lines.** Each change is a spring toward a new target. A moving edge
   can lead on a fast spring and trail on a slow one, so a bar looks like liquid.
3. **Put the keyframes on words.** Each state change is scheduled at a word's time from the transcript.
   Treat word times as estimates, about ±0.2 s.
4. **Make a framing call for every clip, and write down why:**
   - **Full-frame cutaway** (3–10 s) when the line describes something to *see*: a product, a process, a
     comparison, a chapter change. Not in the first second of the hook, not on personal or opinion lines,
     and with at least ~2 s of face between cutaways.
   - **A panel in the empty space** (transparent) when the edit already leaves room beside the speaker.
     It can run long, because the speaker stays on screen.
   - **Nothing** when the line is about the speaker.
5. **Plan before drawing.** A table with one row per clip: in and out times, the line it covers, what the
   shape does on which words, the treatment, and why. A person approves the plan before any clip is built.
6. **Match the video exactly:** the same resolution and frame rate.

It MUST NEVER invent a number, quote, price, or result. Use relative bars, placeholder text lines, or labels
taken straight from the transcript, and list everything illustrative. Real figures go on screen only when
the narrator supplied them.

---

## How you know it worked

- [ ] **Words and motion agree.** Pick five changes; each lands within about a quarter second of its word.
- [ ] **Renders repeat.** Render the same clip twice; the frames match.
- [ ] **Nothing is invented.** Every number on screen is either in the transcript or labelled illustrative.
- [ ] **The panel never touches the speaker.** Check the first, middle, and last frame of every panel clip.
- [ ] **Before and after, side by side.** The same stretch with still slides and with motion, watched by a
      person, who prefers the motion version. This is the only acceptance criterion that really matters.

| Measure | Target (not yet measured here) |
|---|---|
| Word-to-motion drift | < 0.25 s |
| Clips per minute | 4–7 (medium density) |
| Render time per 10 s clip | minutes, not hours |

---

## Known hard parts (the scars)

*None of our own yet.* These are the traps we expect, from reading the engine and from our other video
stations:

- **Word times from a caption file are rounded to the line, not the word.** Get real word timings from a
  local speech-to-text model; that is the step most setups skip.
- **A speaker box that moves or resizes mid-section** breaks a long panel clip. Detect it and split the
  panel, or size for the largest box.
- **Transparent video needs an encoder that supports transparency.** Check before the first long render.
- **Setup scripts that change the computer's system Python.** Install a new engine inside its own isolated
  environment.
