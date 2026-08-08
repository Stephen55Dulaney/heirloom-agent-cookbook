# Recipe: The Hero Plate (Hero Image Prompt)

> The one shot that stops the scroll. Everything the brand wants to say, compressed
> into a single image a machine can actually render.

## What you're cooking

You have a product and a feeling you want people to have when they see it. What you
*don't* have is the one striking picture that carries that feeling — the hero image at
the top of the landing page, the shot that does the work before a single word is read.
Describing it to an image model is harder than it looks: pile in brand strategy and
mood words and the model renders mush.

This recipe turns your creative brief into a **tight, image-native prompt** — the exact
text you paste into an image generator (gpt-image, Imagen, DALL·E, or similar) to get a
polished, magazine-quality hero shot. It thinks like a photographer, not a marketer:
scene, subject, light, lens. Everything a camera can't capture gets left on the cutting
room floor.

Paste this card into Claude Code or Codex, point it at your brand, and say "do this for
my product." You'll get back a scene description, composition specs, a small palette, and
one final paragraph ready to hand straight to the image model.

## Before you start

The AI should gather context before writing a single line of the prompt:

- **The Mother Stock** — read `recipes/marketing/product-marketing-context.md` if it
  exists. This is the master positioning document: brand voice, audience, what the
  product is and who it's for. It anchors everything.
- **The Plating Guide** — read the creative brief at `recipes/marketing/creative-brief.md`
  if it exists. This carries the color palette, mood-board description, art-direction
  notes, and visual-tone keywords — the raw material this recipe compresses.
- Only after reading those, ask the human for what's *missing*: a specific product to
  feature, or a scene they already have in mind. Don't re-ask for anything the two
  documents already answer.

## The method

The whole craft is **stripping strategy down to things a camera can see.** "The brand
should feel approachable" is brand-voice copy — useless to an image model. The image
version is "warm afternoon light, hands visible, lived-in objects on the surface."
Concrete nouns beat adjectives every time: "a ceramic mug with a chipped rim" renders;
"a mug that feels honest" does not.

Build the output in these parts, in order:

**Visual concept** — one paragraph describing the *scene* in a photographer's language.
Where is the subject placed (left third, center, foreground)? What is it doing (holding,
walking, looking)? What's the setting, and what's the light doing — direction, time of
day, warmth? Begin the paragraph with a line that tells the model this is a hero image
for a landing page: polished, professional, magazine-quality, no text or logos.

**Composition specs** — three to five bullets: aspect ratio (landscape 16:9 or 3:2 for
hero use), camera framing (medium shot, wide establishing, top-down flat lay), depth of
field (shallow with soft background blur, or everything sharp), where to leave empty
"negative space" for the headline and button to sit later, and lens character (a 35mm
film look, an 85mm portrait compression).

**Color palette** — four to six colors, no more. Each on its own line as a hex code with
its job: for example "#5B7C5A — moss accent in the foliage." Pull only the colors that
will actually appear in *this one shot*; skip the rest of the brand palette. Never write
"earthy green" — write the hex code.

**Mood and atmosphere** — two or three adjectives that translate to visible pixels:
"warm, lived-in, gently chaotic, golden." Not "approachable, modern, trustworthy" —
those don't render.

**Negative prompts** — three to five short "avoid this" bullets: no text or signage, no
clinical/sterile look, no oversaturated AI-glow lighting, no cluttered foreground.
Because image models can't reliably draw text, *negative-prompt* any typography rather
than asking for it.

**The final prompt** — a single flowing paragraph, no headers or bullets, that folds the
scene, the key composition specs, the palette inline, and the mood into the literal text
you send the model. Keep it under 400 words; most models lose the thread past roughly 500
tokens of instruction. Commit to **one concept** — pick the single strongest image, don't
stack three competing scene ideas.

## Acceptance Criteria (how you know it worked)

- [ ] The final prompt is a single paragraph, no markdown, and under 400 words.
- [ ] It opens by declaring a hero image, magazine-quality, with no text or logos.
- [ ] Every color is a hex code with a stated role — no vague color names anywhere.
- [ ] The scene is one committed concept, not several stitched together.
- [ ] Negative space for headline and button placement is called out in the composition.
- [ ] No typography, logo, or brand-strategy language survives into the prompt.

## Primary metric

`render_ready` — can the final prompt be pasted into an image model with zero edits and
produce a usable hero on the first try? One clean paste, one usable shot. Yes wins.

## The bright lines (never cross)

- **Strip strategy.** Brand voice, do/don't lists, and typography systems live in the
  brief — never in the image prompt.
- **Hex codes only.** Never "earthy green." Always "#5B7C5A — its role."
- **No text or logos requested.** Image models can't render them reliably; negative-prompt
  them instead.
- **One concept per prompt.** The strongest single image, fully committed — never three
  ideas competing for the frame.
- **400 words is the ceiling** for the final prompt. A tight prompt beats a verbose one
  nearly every time.

---

*A good hero image says the whole thing before anyone reads a word. Give the model a
scene it can photograph, not a strategy it has to interpret — and the money shot comes
back on the first plate.*
