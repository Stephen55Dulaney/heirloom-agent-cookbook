# The Code-Free Repo: Why the Next Open Source Contribution Is Just a Recipe Card

*Heirloom Agent Cookbook — founding essay, 2026*

---

## The idea

The Heirloom Agent Cookbook is an open source repository designed from the ground up to
contain **no code** — only **Recipe Cards**: behavior contracts, acceptance criteria,
performance thresholds, and persona definitions that describe *what a system must do* without
specifying *how it should be implemented*.

The code that runs these recipes is not the artifact. It is the response.

This is not a documentation repo, and it is not a spec sheet. It is a **challenge** — and the
challenger is every model and every builder who wants to prove they can make something that
passes. A Recipe Card keeps the warmth of a recipe and the spine of a contract: it reads like
a recipe, but it has tested acceptance criteria and real performance thresholds, and it can
be won.

---

## The problem with code

Open source changed software forever. Linus Torvalds didn't just share Linux — he shared a
*way of working* that turned individual contributions into collective infrastructure. For
thirty years, the atomic unit of open source was the **commit**: a concrete change to
concrete code.

Then something shifted. Models got good enough to write production-quality code from a
description. Then better. Then faster. A skilled practitioner could describe a working system
in a markdown file and watch a model implement it in hours — and then *regenerate* the
implementation from scratch every time, correctly, on a new platform, in a new language, for
a new context.

The code became ephemeral. The description didn't.

---

## The observation that started this

We were building a voice pipeline for a companion device — a small, warm, patient presence
for people navigating serious illness. The feature we were trying to ship was the simplest
possible thing: **speak.** Say one full sentence out loud to the person in the room.

We had it working. We had it working three times, on three machines, and every one was broken
a different way: one chopped the last word off, one pushed audio through the wrong mixer, one
synthesized in chunks that truncated mid-thought. Three devices. Three renderings. Three bugs.

Here's the part that stayed with us. The system that builds our companions regenerates its
own code — you hand an agent a contract and it rewrites the capability on its own box. So
every hard-won fix could be silently un-written the next time it regenerated. **The code was
not the knowledge. The contract was.** And we didn't have a canonical place to put the
contract. When we tried to write one, we found something surprising: writing a *good* contract
— tight enough to fail the wrong implementations and pass the right ones — was harder than
writing the code. And once written, it was worth far more than any single implementation.

So we asked: what if we open-sourced *that*?

---

## What a Recipe Card is

A Recipe Card is a single markdown file that answers four questions:

1. **What does this feature do?** Plain-language behavior description.
2. **How do we know it works?** Acceptance criteria — specific, testable, observable.
3. **What does it cost?** Performance thresholds — latency, memory, failure behavior, with one
   primary metric that decides the champion.
4. **What must it never do?** Invariants — the non-negotiables, anchored to the Care Doctrine,
   that no implementation may violate.

It carries one more thing the research specs below mostly don't: the **scars** — the exact,
named ways the capability has broken on real hardware, written as honest field notes so the
next builder doesn't rediscover them the hard way.

No imports. No function signatures. No language. No framework. Just the shape of what correct
behavior looks like, plus the receipts.

---

## Where this sits on the map (the honest part)

We are not the first to notice that contracts can outrank code. We want to say that plainly,
because knowing the landscape is a credibility move, not a confession.

The idea that **specs and contracts are the durable, first-class artifact** is, right now, an
active research frontier:

- **Agent Behavioral Contracts (ABC) / AgentContract-Bench** applies design-by-contract to AI
  agents — preconditions, invariants, governance policies, and recovery as first-class,
  runtime-enforceable components, evaluated across many models and vendors. This is strikingly
  close to our core bet.
- **CodeSpecBench** benchmarks executable behavioral-spec generation, with execution-based
  evaluation — the "code is ephemeral, the spec endures" thesis, made measurable.

So we do **not** claim to have invented the mechanism. The frontier already proves that
contracts beat code. What that frontier *validates* is our bet; what it doesn't yet contain is
the thing we're actually building.

**What doesn't exist is the combination, and the combination is the novelty:** an **open,
community contest** where the repo *is* the benchmark and anyone can submit; where the
**contract is the product** and the code is disposable and hosted elsewhere; where a **moral
care invariant — the Care Doctrine — is a first-class artifact**, not an afterthought; grounded
in **real companions in real homes** on cheap, real hardware, scars and all; and **accessible
to a no-code beginner** who reads a card, talks to an AI, and builds it. The Heirloom Agent
Cookbook is the **no-code, community, care arm** of a real and hot research frontier — not a
lone crank claiming a first.

---

## The contest mechanic

When you contribute here, you are not publishing code. You are answering a challenge: *can you
build something that passes this?*

A builder reports an implementation ("here's mine, it clears `R-001` at this number"). A model
is run against a card and its output is evaluated. A platform posts its own passing result. The
repo becomes a **benchmark over time** — the contracts don't change; the implementations
accumulate around them, in the open. You can see which models, which platforms, which
architectures reliably produce correct behavior, and which don't. The Hall of Fame keeps the
belt for each card.

---

## The Care Doctrine: the non-negotiable invariant

The founding cards describe a companion for people navigating serious illness. That context
required something a pure technical spec doesn't have: a **moral invariant.** There are things
this system must never do regardless of implementation — not for performance reasons, for human
reasons.

The Care Doctrine is that invariant, compressed to four rules, each with a one-line check a
model can hold in working memory: **never correct their reality; never pretend; the person owns
their story; a friend first.** Every Recipe Card carries the doctrine check: *does any
acceptance criterion, if passed, violate a doctrine rule?* If yes, the card is wrong and must be
fixed before it ships. A human-centered moral constraint as a first-class artifact inside the
specification itself — that is the part the cookbook treats as load-bearing.

---

## The strongest objection: Goodhart's Law

When a measure becomes a target, it stops being a good measure. If you publish acceptance
criteria and let models optimize against them, you should expect implementations that pass the
*test* without honoring the *intent* — code that games the metric.

We don't pretend to solve this. We mitigate it, deliberately and in layers, and we'd rather say
exactly how than wave it away:

- **The Care Doctrine invariants** are prohibitions, not checkboxes — much harder to game than a
  threshold, and they outrank every performance number.
- **Multiple metrics plus hard gates** mean you can't win by being fast and broken: a
  truncated-but-quick "speak" fails a gate and never reaches the board.
- **A human vibe-gate** reads each submission against the spirit of the doctrine, not just the
  letter — a person, not a script, decides if it actually feels like care.
- **Real hardware** performance, measured on a real device, makes synthetic gaming visible.
- **The scars** — the named known failure modes baked into every card — make the most common
  cheats expensive and obvious, because the very tests that catch them are written down.

Together these don't eliminate Goodhart's Law; they make gaming **expensive and visible**, which
in an open, public forum is most of the battle.

---

## Why it matters

If this works — if Recipe Cards become a shared vocabulary for *what software should do*,
independent of language, platform, and model — it changes the economics of contribution in
three ways. Contribution becomes **language-agnostic**: writing a card requires knowing the
*behavior*, which lets clinicians, educators, and ethicists contribute precise specifications
without writing code. Evaluation becomes **community property**: the criteria live in the open
and the results accumulate in public. And **the recipe outlives the meal**: code rots,
dependencies break, languages evolve, but a clear behavioral contract can be re-implemented
fresh on whatever platform comes next. The spec for how a companion should speak to a sick
person at three in the morning should not become unreadable when the language it was first
written in goes out of fashion.

That is the heirloom: an agent built to live at home, and to outlive its maker.

---

## What's in the cookbook today

- **A front door** — what this is and why it matters.
- **The Care Doctrine** — the non-negotiable, four-rule invariant, shown in two realities
  (an elder, a child).
- **A build recipe** — how a companion was built in three and a half hours from these cards.
- **The founding Recipe Card, `R-001: Speak`** — what "speak" means, with its scars.
- **Two personas** — the elder companion and the child companion.
- **Four open cards** — memory, intake, dashboard, display — waiting for their first author.
- **A Hall of Fame** — the leaderboard, and the current `R-001` champion to beat.

The code is the response to the contract. The contract is the thing worth keeping. If you have
a piece of software that matters to you — something that must never fail, must never lie, must
always show up — write the recipe. Open-source it. Let the models cook.

The meal is ephemeral. The recipe is how you feed people forever.

*— Stephen Dulaney & Scout, Genesis Lab, 2026. The devil's advocate is welcome. If you can
break this argument, tell us — that's how the contract gets harder.*
