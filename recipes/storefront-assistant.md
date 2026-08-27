# Recipe: A Storefront Assistant That Shows Its Work

**Mise en place.** Everything in its place before the heat goes on.

A line cook who starts chopping when the ticket arrives is already behind. The prep is not
preparation *for* the cooking — the prep is most of the cooking, and the part that decides whether
the dish is any good. This recipe is that idea applied to an agent: **you write down how you will
know it worked before you write the thing.**

---

## What you're building

A shopping assistant that sits on an existing storefront and helps someone who does not yet know
what to search for. It works on any catalog of parts that must be chosen together — bicycle
components, camera systems, plumbing fittings, PC builds. Anywhere the customer's real question is
*"will these two things work together?"* rather than *"do you have this in blue?"*

**It is not a chatbot with a product list in the prompt.** The difference is that this one can be
checked.

---

## Step 1 — Find out what the catalog actually knows

**Before any design.** Open one product record and read every field. Then open one from a different
category and read that.

You are looking for the fact that decides the architecture: **is the thing you need to filter on
actually in the data?** Not "could a model guess it" — *is it there, in a field, consistently.*

Expect it to be encoded unevenly. One category will carry it in the title. Another will carry it
only in prose, and only as a term of art an outsider would not recognise. A third will not carry it
at all — and that third one is usually not a gap. Some parts genuinely fit everything, and a
category with no compatibility signal is telling you something true.

**Hand the model the raw records and ask it to report what is present, not what it can infer.**

> **The rule:** if you cannot point at the field, you are about to build a taxonomy, and that is a
> different and much worse project than the one you were asked for.

---

## Step 2 — Write the acceptance criteria before you write anything

Six or so. Each one a sentence someone could disagree with. Each one checkable by a machine or by a
person in under a minute.

Two of them must be **negative**:

- **One thing that must NOT happen.** A part that fits everything must not acquire a fake
  constraint. An unrecognised phrase must degrade to *no filter*, never a *wrong* filter — a wrong
  filter silently hides what the customer asked for, which is worse than not filtering at all.
- **The inverse of your main case.** If a street part correctly returns street parts, run the
  downhill one too. **One example passing proves nothing.** This is the criterion that catches a
  filter that was never applied, because a system doing nothing can look perfect on the happy path.

**Get these agreed out loud before proceeding.** With a client, with a colleague, with yourself in
writing. The disagreement you have now is cheap; the one you have after building is not.

---

## Step 3 — Derive, do not author

Whatever you found in Step 1, compute it from the product text at build time. Do not hand-write a
mapping table.

A mapping table is a second source of truth. It drifts from the catalog the moment someone adds a
product, and **nothing tells you it has drifted.** A derivation means a new product classifies
itself, and the test suite fails loudly if the vocabulary ever changes.

**Same rule for anything derived from behaviour**, not just compatibility.

---

## Step 4 — Hard constraints run before similarity, never after

Semantic search is very good at meaning and very bad at *"under sixty dollars."* Both are prices;
they embed alike. Filter first, rank what survives.

**Extract stated constraints deterministically.** Regex, not a model call. "Under fifty" is a
promise to the customer, and paying latency and tokens for a model to *probably* honour it is worse
on every axis.

Two details that only show up in practice:

- **Require a currency marker.** Catalogs are full of numbers that are not prices — sizes,
  hardness ratings, widths. Reading one as a budget hides products the customer asked for.
- **"Under" excludes the boundary; "up to" includes it.** The words differ, so make the filter
  differ. Someone will check.

> **The rule:** anything that is a promise to the customer is deterministic. The model is for
> language and judgement, not for keeping promises.

---

## Step 5 — Compute readiness instead of guessing it

Two numbers from the session, no model involved:

- **Category variance** — how spread out their browsing is across categories. High means they have
  not decided what *kind* of thing they want.
- **Item variance** — inside the category they keep returning to, how many distinct items. Low, with
  repeats, means they are circling two or three and close to deciding.

That gives you three modes, and **the mode must change the shape of retrieval, not just the tone.**
A "where do I start" turn should be capped so it cannot return eight of the same category. A
"help me decide" turn should pin the two items they keep coming back to.

**Add hysteresis.** One stray click must not flip an established mode.

---

## Step 6 — Propose, never execute

The assistant may suggest an action. Only a human click performs one.

Two gates, and they are different in kind:

- **A standing permission**, off by default for anything that spends money or changes state.
- **A per-action confirmation**, every time.

**Enforce the permission by absence.** Do not instruct the model not to do something — simply do not
hand it the tool. A capability the model was never given cannot be used, no matter how the customer
phrases the request. Test it that way: turn the permission off, then ask for the action insistently,
and confirm nothing was even offered.

**And make the confirmation falsifiable.** Name the feature that distinguishes this item from its
nearest neighbour, not just the product name. Two products one letter and ten dollars apart, sitting
next to each other, are how a confirmed choice becomes the wrong purchase.

---

## Step 7 — Put the receipts on screen

Every answer should carry what produced it: which mode, how many candidates survived the hard
filters, which model answered, and exactly which records it was allowed to see.

This is not a debug panel you remove before launch. **It is the instrument that makes a wrong answer
visible**, and it will find things no test does — because a model papering over a broken filter
produces prose that reads perfectly.

---

## What the model produces

Hand these steps to a coding agent, one at a time, and it writes: a build-time derivation and its
test, a constraint extractor and its test, a readiness calculator, a retrieval function, a streaming
route, and a panel that renders the receipts.

**Give it Step 2 first and make it show you the criteria passing before it writes Step 3.**

---

## Known hard parts (the scars)

- **A filter that exists and is never set.** The machinery type-checks, the tests pass, the answers
  read beautifully, and the search runs over everything. Found by reading a candidate count, not by
  reading a reply.
- **Counting tokens that you cannot see.** A response ceiling includes the model's reasoning. Set it
  for brevity and replies stop mid-sentence, tool calls never complete, and it presents as an outage.
  **Brevity is an instruction. A ceiling is a cut.**
- **Two owners for one piece of state.** The panel read one source and the prompt read another, and
  they disagreed on screen in the same second. *If these two disagree, which one is right?* If you
  cannot answer instantly, you have two owners.
- **A gate that was never installed.** It reports nothing, which is indistinguishable from a gate
  that passed. After you add one, **reintroduce the bug on purpose and watch it fail.** A gate nobody
  has seen fail is a claim, not a check.
- **A red test that is wrong.** More dangerous than a green one that is wrong, because you will
  "fix" working code. Check whether the test or the subject is broken *before* you touch anything.
- **The model describing its own context accurately and misleading the customer anyway.** It said
  "all eight options" because it received eight, when nine had matched. Tell it both numbers.

---

## The rule

**Write down how you will know it worked, out loud, before you write it.**

Everything else on this card is a consequence of that one habit. The negative criteria, the
derivation over the mapping table, the receipts on screen, the gate you watched fail — each is a way
of making a claim checkable by someone who was not there when you made it.

A dish you cannot taste until service is a gamble. **Mise en place is how professionals stop
gambling.**
