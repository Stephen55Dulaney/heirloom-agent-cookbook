# Recipe: The Sizzle Reel (Motion Direction & Storyboard)

> Fifteen seconds, shot by shot. A storyboard tight enough for a machine to build the
> video, loose enough to let it find the look.

## What you're cooking

You want a short marketing reel — the fifteen-second clip that loops on a landing page or
plays in a feed. But "make me a video" is not something you can hand to a tool and get
back anything good. Motion needs a plan: what's on screen at each moment, how it moves,
how it feels, and where it lands.

This recipe produces a **storyboard** — a scene-by-scene plan for a 15-second reel, timed
down to the frame, that another tool or AI can turn into actual video (a code-based video
generator like Remotion, an After Effects timeline, or a generative video model). It's
specific about timing and beats, and evocative about mood — enough structure for the
downstream tool to make confident choices, enough freedom for it to interpret the look.

Paste this card into Claude Code or Codex, give it your brand and your one hero image, and
say "storyboard my reel." You'll get a story arc, a precise scene table, and direction for
motion, type, color, and the closing call-to-action.

## Before you start

The AI should gather context before storyboarding:

- **The Mother Stock** — read `recipes/marketing/product-marketing-context.md` if it
  exists: the master positioning, voice, and audience.
- **The Plating Guide** — read the creative brief at `recipes/marketing/creative-brief.md`
  if it exists, for the palette and visual tone.
- **The landing page copy**, if available — its hook and value propositions are the verbal
  scaffolding for the reel and the source of the closing line.
- You have exactly **one rendered hero image** to work with (see The Hero Plate). Plan
  around that single image — assume no other product photos, portraits, or B-roll exist.
- Only after reading those, ask for anything still missing. Don't re-ask what the
  documents already cover.

## The method

Start with the **story arc**: one sentence naming the emotional shape of the fifteen
seconds, then the through-line — what the viewer feels or wants by the end. For example,
"Hook → tension → reveal → resolution → call to action; viewer feels permission, not
pressure," or "Empty state → discovery → delight → CTA; viewer feels FOMO without being
yelled at."

Then the load-bearing artifact: a **scene breakdown table** of exactly four to five scenes
covering 0:00 to 0:15. Video runs at 30 frames per second, so the whole reel is **450
frames**, and the scenes must add up to exactly that. Give each scene a row: its number,
its time range, its frame range, what's on screen, one motion verb, and a one-word mood
beat. A few firm rules:

- Frames must total 450. Overlap the handoffs — each new scene starts 5 to 15 frames
  before the previous one ends, so cuts feel seamless.
- Each scene gets **exactly one** motion verb: zoom, slide, pulse, wipe, rotate, parallax,
  scale, or blur. Pick one; don't stack.
- The mood beat is a single word — how the viewer should feel right at that moment
  (curious, calm, delighted).
- End the table with a final **60-frame "settle"** that holds steady. If rendering runs
  long, that steady hold is the safe default.

Then the supporting sections. **Hero image usage:** name which scenes the one hero image
appears in, how it's framed (full-bleed background, masked into a circle, parallaxed at
half speed), and what it must *not* do (for instance, never used as the literal product
shot — only as atmosphere). **Motion vocabulary:** three to five default idioms the
downstream tool should reach for — the easings for entrances versus crossfades, gentle
spring settings, and forbidden patterns (no rotating spirals, no parallax beyond 1.5×, no
flashing). **Typography direction:** one or two system-safe fonts (for example, Georgia for
headlines, plain system text for support), plus hierarchy and letter-spacing notes.
**Color in motion:** two or three hex codes from the brief, each with its job — background,
entrance accent, text contrast. **CTA frame:** exactly what appears in the final beat — a
headline of three to six words, an optional sub-line of eight to twelve, and one implicit
visual cue (an arrow, a scroll-down hint).

Two habits keep it usable: be **concrete about timing** — "frames 180–230," never "around
the middle" — and stay **frame-driven**, since the downstream tool works in frames, not
timers or loops.

## Acceptance Criteria (how you know it worked)

- [ ] The scene table has 4–5 scenes and the frame counts sum to exactly 450.
- [ ] Scene handoffs overlap by 5–15 frames, and the reel ends on a 60-frame settle.
- [ ] Every scene has exactly one motion verb and a one-word mood beat.
- [ ] The single hero image is assigned to specific scenes, with a stated "does not do."
- [ ] Timing is given in frame ranges, never vague phrases like "around the middle."
- [ ] The CTA frame names exact on-screen text within the word limits.

## Primary metric

`buildable_first_pass` — can a downstream video tool take this storyboard and render a
coherent 15-second reel without asking a single clarifying question? Yes wins.

## The bright lines (never cross)

- **Frames total 450**, always — 15 seconds at 30fps, no rounding.
- **One hero image, one feature.** No extra photos, portraits, or B-roll exist; plan
  around the single image.
- **One motion verb per scene.** No stacking effects into a single beat.
- **Concrete timing only.** Frame ranges, never "around the middle."
- **Always end on a 60-frame settle** so a long render has a safe steady default.

---

*A reel lives or dies in the timing. Give the machine a frame-accurate map and one honest
image to build from, and fifteen seconds becomes a story instead of a slideshow.*
