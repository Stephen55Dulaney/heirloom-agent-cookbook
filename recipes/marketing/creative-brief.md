# Recipe: The Plating Guide (Creative Brief)

> The dish is cooked; now decide how it's plated. Color, type, mood, and the one-line story —
> the visual identity every creative reads before they touch a pixel.

## What you're cooking

You know a great restaurant partly by the food and partly by everything around it: the plate, the light,
the typeface on the menu, the story the room tells. Your product has the same two halves. This recipe
builds the second one: **a complete creative brief that defines your brand's visual identity — colors,
fonts, mood, art direction — and the story hook that makes someone stop scrolling.**

The pain it solves is drift and inconsistency. Without a brief, every landing page, email, and ad gets
designed from scratch, and they slowly stop looking like the same company. This recipe produces one
document a designer (or the next AI) reads before making anything visual, so it all comes out of one
coherent identity. It's written to be inspiring to a human *and* precise enough that an automated design
system can parse the exact colors and fonts.

Paste this card into Claude Code or Codex and say "make my Plating Guide." The AI acts as a senior brand
strategist and art director and produces the brief.

## Before you start

**Read The Mother Stock first** (`recipes/marketing/product-marketing-context.md` — the master
positioning document). If it exists, it already holds your audience, your brand voice adjectives, your
proof points, and how customers talk. Draw the brand personality and story straight from there, and only
ask the human for what's genuinely visual and not yet captured — do they have brand colors already, logo
assets, fonts they love or hate, competitors whose look they want to stand apart from. If no Mother Stock
exists, offer to build it first; positioning should precede plating.

## The method

A complete brief has these parts, in order:

- **Brand story hook.** Start with *why the brand matters*, not what it sells. Frame it through tension
  and curiosity, using one of four formulas: a **surprising stat** that reframes the problem; a
  **provocative question** that challenges an assumption; **the tension** between reality and aspiration;
  or a **contrarian take** that flips conventional wisdom. The hook should make someone stop scrolling.
- **Brand personality.** Define the brand as if it were a person: 3-5 voice adjectives (e.g. "warm,
  grounded, quietly confident"), a placement on two axes (Formal ↔ Casual, Reserved ↔ Expressive), and one
  of the 12 Jungian archetypes (Creator, Explorer, Sage, Hero, and so on) with a reason it fits this
  audience.
- **Color palette — exactly 5 colors.** A primary (calls-to-action, key accents), a secondary (supporting
  elements), an accent (highlights and hover states), a background, and a text color, each with a hex code.
  For each, say why the hue fits the personality, where it should and should *not* be used, and confirm the
  text-on-background contrast meets **WCAG AA** accessibility as a minimum. (These are delivered as design
  tokens so an automated system can read them.)
- **Typography system.** A headline font, a body font, and an accent font (for data, labels, callouts),
  plus a size scale (from a large H1 down to captions) and three weights. Explain why the pairing works and
  reference widely available web fonts (Google Fonts or similar), not exotic licensed ones.
- **Mood board in words.** Describe 3-5 reference images so vividly a designer could find or recreate each
  — composition, lighting, color, subject, emotional tone, and why it captures the brand. Do not link to
  images; describe them, 2-3 sentences minimum each.
- **Visual tone keywords.** 5-7 "this BUT NOT that" pairs that fence the identity in — "earthy but not
  crunchy," "premium but not exclusive," "scientific but not clinical." These pairs stop the brand drifting
  into adjacent-but-wrong territory, the most common visual failure.
- **Art direction notes.** Concrete calls: photography vs. illustration and the ratio; image treatment
  (saturation, grading, filters); layout style (grid, organic, editorial, asymmetric); icon style and
  stroke weight; a white-space philosophy (airy vs. dense); and a motion personality if animation applies.
- **The multiplier sentence.** One sentence connecting the look to the campaign, in the form: a specific
  visual choice + a specific messaging strategy = an outcome neither achieves alone. This links the brief
  to the downstream landing pages, emails, and ads it will govern.

Wrap the whole thing in a short narrative that explains how each visual choice serves the strategy — the
brief should read as one argument, not a checklist.

## Acceptance Criteria (how you know it worked)

- [ ] **A story hook leads** — the brief opens with tension or curiosity about *why the brand matters*, using one of the four formulas, not a feature list.
- [ ] **Exactly 5 colors** are specified with hex codes and per-color usage rationale.
- [ ] **Contrast passes AA** — text-on-background color pairs meet WCAG AA, stated explicitly.
- [ ] **Three fonts, all widely available** — headline, body, accent, each with a reason, referencing real web fonts.
- [ ] **3-5 mood images described in words** vividly enough to recreate, with no image links.
- [ ] **5-7 "but not" tone pairs** are present, fencing the brand out of adjacent-but-wrong territory.
- [ ] **One multiplier sentence** ties the visual identity to the marketing campaign.

## Primary metric

`coherence` — can a designer take this brief cold and produce a landing page that looks like it belongs to
the same brand as the emails and ads, without asking a follow-up question? If yes, the plating guide works.

## The bright lines (never cross)

- **Never invent brand facts the founder didn't confirm.** Personality and archetype are proposals; if the
  human already has colors, fonts, or a logo, honor them rather than overriding with your own taste.
- **Accessibility is not optional.** Any text-on-background pairing that fails WCAG AA doesn't ship — fix
  the color, don't wave it through.
- **Describe the mood board, never link stolen images.** The deliverable is words a designer can act on,
  not a pile of borrowed pictures.
- **Stay inside the positioning.** The visual identity must serve the brand voice and audience from The
  Mother Stock — don't design a look for a different product than the one you're marketing.

---

*Cooking and plating are different crafts, but the diner experiences them as one meal. Get the Plating
Guide right and every later recipe knows exactly how to set the table.*
