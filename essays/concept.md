# The Concept: A Cookbook With No Code In It

*Heirloom Agent Cookbook — concept note, 2026*

---

## The idea, in one line

A public repository that contains **zero code** — only **Recipe Cards** that describe what a
capability must do, precisely enough that any model, on any platform, can build it.

Each card carries: the intent (the human *why*), tested acceptance criteria, performance
thresholds, the edge cases that must not break, and the scars — the honest field notes about
how it has broken before. Anyone, human or model, can attempt to implement the card. The card
is the standard. The code is a submission.

---

## Why it's a different kind of repo

Almost every repository today is **code, plus maybe some docs**. This one is **contracts, and
the code lives somewhere else entirely.** The recipe is the artifact; the code is a response to
it.

That inversion tracks a real shift in how software gets made:

- The old world: you needed a team to write the code.
- The new world: you hand the contract to a model and it writes the code.
- This cookbook: **the contract itself is the open source contribution.**

The recipe stays warm and readable; the contract underneath stays rigorous and falsifiable. A
doc can be vague and still ship. A Recipe Card has acceptance criteria — it can be *failed*, and
that's the whole point.

---

## What a card contains

Each card is a single markdown file with a stable shape:

- **Intent** — one or two paragraphs. Why does this exist? What human need does it serve? If you
  can't say why it matters to a person, it isn't ready.
- **Contract** — the non-negotiable behavior. What it must always do, including how it must fail.
- **Acceptance criteria** — observable, testable pass conditions a person could check by
  watching or listening, not by reading code.
- **Performance thresholds** — minimum, target, and stretch numbers, with one **primary metric**
  that decides the champion (and whether lower or higher wins).
- **Known hard parts (the scars)** — the exact ways it has broken in real life, with the fix and
  the test that catches each one.
- **Doctrine checks** — the moral invariants from the Care Doctrine, which outrank every number.

The `contracts/_TEMPLATE.md` file in this repo is exactly that shape, blank, ready to fill.

---

## The contest

A card with no passing implementation is **open**. Anyone can submit one — built in any
language, on any platform, hosted in their own repo or gist, never here. A submission has to
clear the card's hard **gates** (pass/fail conditions) and then **meet or beat** the current
champion on the primary metric. The best result for each card is recorded in the Hall of Fame,
and the next builder tries to take the belt.

The contest *is* the contribution. Over time the community learns which models, which prompting
styles, and which architectures win on which cards — in the open, where anyone can check.

---

## Why now, and why this domain

Models read repositories natively, pull requests are a natural submission format, and the whole
thing costs nothing to host and has no code to maintain — it only gets more valuable as
implementations accumulate around the contracts.

The founding cards describe a **companion device** — a warm, patient presence for people
navigating serious illness — because that domain demands the one thing a pure technical spec
lacks: a **moral invariant.** The Care Doctrine is that invariant, and making it a first-class
artifact in the spec, grounded in real companions in real homes on cheap real hardware, is what
makes this a cookbook for care and not just a benchmark.

---

## The first move

Read the Care Doctrine. Read `R-001: Speak`, the founding card — the three-broken-machines story
is its origin, and the card writes itself from that pain. Then pick an open card, hand it to a
model, build it, and come meet or beat the champion.

The companion story is the perfect seed: we had "speak" working three times on three machines,
broken three different ways, and the lesson wasn't a better cage — it was a better contract.

*Drafted in the Genesis Lab, 2026.*
