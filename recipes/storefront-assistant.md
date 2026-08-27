# Recipe: A Storefront Assistant That Shows Its Work

### Verification-first architecture

**Mise en place.** Everything in its place before the heat goes on.

A line cook who starts chopping when the ticket arrives is already behind. The prep is not
preparation *for* the cooking — the prep is most of the cooking, and it is the part that decides
whether the dish is any good. This recipe is that idea applied to an agent: **you write down how you
will know it worked, and then you build toward that.**

---

## How to cook this: verified slices

**Build one slice at a time, and let each slice prove itself before the next one starts.**

Hand a coding agent Step 2 and stop. Ask it to show you the criteria passing on their own, with
nothing wired to anything. Then hand it Step 3. Then Step 4.

A specification written all the way to the end before anything runs is a lovely document and an
untested one. **Working software that satisfies two criteria beats a plan that satisfies twelve on
paper.** Every step below is written so it can stand alone and be checked alone.

---

## What you're building

An assistant that sits on an existing storefront and helps someone who knows the outcome they want
but not the product name. It works on any catalog of parts that must be chosen together — bicycle
components, camera systems, plumbing fittings, PC builds. Anywhere the real question is *"will these
two work together?"* rather than *"do you have this in blue?"*

**It is a retrieval system with a conversational surface.** Deterministic code keeps the promises,
the model handles language and judgement, and every answer carries the evidence that produced it.

---

## Step 1 — Find out what the catalog already knows

**Before any design.** Open one complete product record and read every field. Then open one from a
different category and read that. Then one you believe fits everything.

You are looking for the fact that decides the architecture: **the thing you need to filter on, in a
field, consistently.**

Expect it to live in different places in each category. One will carry it in the title. One will
carry it only in prose, as a term of art an outsider would not recognise. And one will not carry it
at all — which is usually the catalog telling you something true rather than something missing.

**Record which of four things an absent value means**, because they lead to different systems:

- **explicit** — the value is present and reliable
- **universal** — this part genuinely fits everything, and unrestricted is the correct answer
- **not applicable** — the concept does not exist for this category
- **unknown** — the fact may exist and this record does not carry it

**Ask the agent to report what is present.** Its job at this step is a field-presence report.

> **The rule:** point at the field. When you can name the field, you are building a filter. When you
> cannot, you are building a taxonomy — a larger project that deserves its own scope and owner.

---

## Step 2 — Write the acceptance criteria, and agree them out loud

Six or so. Each one a sentence someone could disagree with, and each checkable by a machine or by a
person in under a minute.

**Two of them earn their place by covering the ways a system can look right while doing nothing:**

- **The universal case.** A part that fits everything comes back unrestricted, and an unfamiliar
  phrase leaves the whole catalog visible and says so in the receipt. **A filter that hides what the
  shopper asked for is the expensive failure**, so make "everything stayed visible" a thing you
  assert rather than assume.
- **The inverse case.** If a street part correctly returns street parts, run the downhill one too.
  **One example passing is compatible with no filter at all** — a system doing nothing looks perfect
  on the happy path. The inverse is what separates a working filter from a coincidence.

**Get these agreed before you proceed** — with a client, a colleague, or yourself in writing. The
disagreement you have now is cheap. The one you have after building is not.

---

## Step 3 — Derive from the catalog, and keep the evidence

Compute the fact from the product text at build time, so **a new product classifies itself the day
it is added.**

**Keep the source span with the derived value** — which field it came from, and the exact text.
That single habit turns every derived fact into something a person can check in one click, and it is
what lets you answer *"why does the system think this?"* six months later.

A build-time derivation stays in step with the catalog by construction. A hand-kept mapping table is
a second record of the same truth, and it moves at a different speed than the first one.

**Have the build fail loudly when the catalog's vocabulary shifts** beyond an agreed threshold. That
turns a silent change in behaviour into a conversation.

---

## Step 4 — Let hard constraints choose the set, and similarity choose the order

Semantic search is excellent at meaning and unreliable at *"under sixty dollars"* — both are prices
and they embed alike. **Filter to the set, rank what survives.**

**Extract stated constraints deterministically.** Regex, not a model call. "Under fifty" is a
promise to the shopper, and deterministic code is how a promise gets kept every time rather than
usually.

Two details that only appear in practice:

- **Require a currency marker before treating a number as money.** Catalogs are full of numbers that
  are sizes, hardness ratings and widths, and reading one as a budget hides products the shopper
  asked for.
- **"Under" excludes the boundary; "up to" includes it.** The words differ, so let the filter
  differ. Someone will check.

**Record how many survived the filters before any display limit is applied.** That number is the
honest one, and you will need it in Step 7.

> **The rule:** anything that is a promise to the shopper is deterministic. The model is for
> language and judgement.

---

## Step 5 — Compute readiness from behaviour

Two numbers from the session, no model involved:

- **Category spread** — how distributed their attention is across categories. High means they are
  still deciding what *kind* of thing they want.
- **Item concentration** — inside the category they keep returning to, how few distinct items. High
  concentration with repeat views means they are close to deciding.

That gives three modes, and **the mode changes the shape of what comes back, not only the tone.** A
"where do I start" turn is capped so one category cannot fill the whole set. A "help me decide" turn
pins the two items they keep returning to.

**Let a mode hold until a new one qualifies twice in a row.** Momentary attention is noise; a change
of mind shows up more than once.

**Treat your first thresholds as hypotheses and tune them against replayed sessions.** Say so in the
code, so the next person knows which numbers were measured and which were reasoned.

---

## Step 6 — The assistant proposes, the human performs

Two gates, different in kind:

- **A standing permission**, off by default for anything that spends money or changes state.
- **A per-action confirmation**, every time, on a real click.

**Grant capability by handing over the tool.** When permission is off, the model is simply not given
the tool — so the outcome holds regardless of how the request is phrased, and you can prove it by
asking insistently and watching nothing be offered.

**Have the confirmation name the feature that distinguishes this item from its nearest neighbour**,
alongside the product name. Two products one letter and ten dollars apart, sitting next to each
other on a page, are how a confirmed choice becomes the wrong purchase.

**Revalidate price, availability and identity at the moment of confirmation**, and re-present
anything that changed while the shopper was reading.

---

## Step 7 — Put the receipts on screen

Every answer carries what produced it: catalog version, mode, the constraints applied, any phrase
that was not recognised, how many records survived the hard filters, exactly which records the model
was given, and which model answered.

**Assemble the receipt from the same snapshot the prompt was built from**, so the two describe one
event.

**Tell the model both counts** — how many survived and how many it received. Given only the second,
it will describe its own context accurately and the shopper will hear something broader than what is
true.

This is a permanent part of the product. **It is the instrument that makes a wrong answer visible**,
and it finds things tests do not, because a model writing over a broken filter produces prose that
reads perfectly.

---

## Known hard parts (the scars)

- **A filter that exists and is never set.** The machinery type-checks, the tests pass, the answers
  read beautifully, and the search runs over everything. Found by reading a candidate count.
- **A response ceiling that counts reasoning you cannot see.** Set it for brevity and replies stop
  mid-sentence and tool calls never complete. **Ask for brevity in the instruction and leave the
  ceiling as a runaway guard.**
- **Two owners for one piece of state.** The panel read one source and the prompt read another, and
  they disagreed on screen in the same second. *If these two disagree, which is right?* If the
  answer is not immediate, there are two owners.
- **A gate reports nothing until it is installed**, which reads exactly like a gate that passed.
  After adding one, **reintroduce the defect on purpose and watch it fail.** A gate you have seen
  fail is a check; one you have not is a claim.
- **A red test can be the thing that is wrong.** Confirm the fixture and the expectation before
  changing the code it is pointing at.
- **The model can describe its own context accurately and still mislead.** It said "all eight
  options" because it received eight, when nine had matched.

---

## A note on how these steps are worded

Every instruction here says where to go rather than what to avoid.

**A prohibition is a rock in the stream.** Water finds its way around a rock — and so does a model,
because "not that" leaves every other direction open, including several you would not have chosen.
Moving the goal works better than blocking a path.

**Say where the ocean is, and let the raindrop find its way.**

The exception is the acceptance criteria, which exist precisely to assert that something did not
happen. **Tests may be negative. Instructions should be positive.**

---

## The rule

**Write down how you will know it worked, out loud, before you build it.**

Everything else on this card follows from that one habit. The two hard criteria, the derivation that
carries its evidence, the receipts on screen, the gate you watched fail — each one makes a claim
checkable by someone who was not there when you made it.

A dish you cannot taste until service is a gamble. **Mise en place is how professionals stop
gambling.**
