# Recipe: A Walkthrough From a Phone Video

### The narrator talks; the slides come from what they said

**One take, two jobs.** The first walkthrough cooked from this recipe answered a "(Video Required)"
field on a job application *and* became the channel's first upload in weeks. It worked for one reason,
and that reason is the whole recipe: **the slides came from the transcript, not from a script.**

A script was written first. The narrator ignored it and talked, and what they said was better, because
it was their system and they had actually been inside it. The machine's job was to cut the digressions,
put the narrator's own sentences on screen at the moment they say them, and stay out of the way.

---

## What you're building

A 4–5 minute architecture walkthrough of one system you built: you in a box on one side, slides beside
you that show what you're saying *as you say it*, with chapters, a thumbnail, and a private upload.

**You bring:** the system's name, one phone take of 5–8 minutes (rambling is fine, "um" is fine), and
three questions to answer. For an application, they're in the posting. Otherwise use *what is it · what
did you choose and why · what did you trade away.*

---

## The contract

Given one raw take of a person explaining their own work, the pipeline MUST:

1. **Transcribe with timestamps before cutting anything**, and read the whole transcript. The transcript
   is the design document.
2. **Find the best line first**, the one nobody would have scripted, and build the cut around
   protecting it.
3. **Cut into 3–5 contiguous blocks**, not twenty snippets, snapped to sentence boundaries so no word is
   clipped. Aim for 4–5 minutes from 6–8.
4. **Recompute every slide time on the cut timeline.** A slide timed to the raw take lands on the wrong
   sentence after the cut; it's the one bug that makes the whole video look sloppy.
5. **Build one slide per beat (8–10 in total) from the narrator's own words**: their number, their phrase,
   their example. Leave a clear column for the narrator's box.
6. **Look at the finished video.** Pull four or five frames and view them before handing anything over.
7. **Upload as private only.** Visibility and publishing belong to the human.

It MUST NEVER narrate for the person or synthesize their voice. If someone says "just make the video,"
the answer is: *I'll build the visuals, you bring the audio.* An AI-narrated walkthrough is a different
thing, and for a hiring video it's a disqualifying one.

---

## How you know it worked

- [ ] **The best line is in.** The sentence you'd quote to a friend survives the cut.
- [ ] **Slides land on their words.** Scrub to five random slide changes; each one appears within about
      half a second of the narrator saying it.
- [ ] **Nothing on screen was invented.** Every number and phrase on a slide appears in the transcript.
- [ ] **The box never covers a slide.** Check a frame from each block.
- [ ] **The upload is private.** Read the visibility back from the platform, not from the upload's
      success message.
- [ ] **No false success.** A render step that "succeeds" without writing a file is caught. The file
      exists, has the expected duration, and you've watched frames from it.

| Measure | Minimum | Target |
|---|---|---|
| Finished length | under 6 min | 4–5 min |
| Slide-to-word drift | < 1.0 s | < 0.5 s |
| Human edits to slide text after review | < 5 | 0–2 |

---

## Before it goes public

- **The privacy pass** (see the wing's README): read the transcript for names, places, and care details,
  including a family's city.
- **The opening line.** If the narrator starts with "this is for a ___ position" and the video is going
  public, say so before it ships: it broadcasts a job search to everyone they're in process with. A cold
  open on the system is a better hook anyway.
- **Whose story is it?** A system running in someone's home is partly theirs. Public needs their okay.
  Raise it once, plainly; then it's the narrator's call.

---

## Known hard parts (the scars)

**1. Phone footage lies about its shape.** It often reports landscape while carrying a rotation flag that
makes it portrait. Check the real geometry after a test encode. Portrait is good news: the narrator sits
in a tall box beside the slides.

**2. A headless browser "succeeded" and wrote nothing.** An old headless mode reported success and
produced no image. Check that the file exists and has pixels, not that the command returned zero.

**3. Stitching still images runs long.** Image-sequence joins can drift past the audio. Force the final
duration to the cut's length.

**4. A sloppy verifier is worse than none.** A search for one word matched a longer word containing it,
and it made us confident about the wrong thing. Check whole words.

**5. Two uploaders, two videos.** The human uploaded by hand while the pipeline uploaded too. Agree who
is doing it before either starts.

**6. The narrator will thank the machine for making them look smart.** Correct it out loud. They said
the good thing; the recipe's only job is to put it on screen when they say it.
