# Contributing

The Heirloom Agent Cookbook ships **Recipe Cards**, not code. There are two ways to
contribute: write a new card, or win an existing one. Both are pull requests. **No code is ever
hosted in this repo** — not yours, not ours. The contracts and the doctrine are the law every
implementation must honor; the code lives wherever you build it.

---

## The contest, plainly

1. **Pick a card.** Browse `contracts/`. A card with no champion is open. The founding card is
   `contracts/R-001-speak.md`; the others (`memory`, `intake`, `dashboard`, `display`) are open
   stubs waiting for an author.
2. **Build an implementation.** In any language, on any platform, hosted in **your own** repo or
   gist — never here. Read `doctrine/care-doctrine.md` first; the doctrine outranks every
   performance number, and a technically-correct build that violates it does not pass.
3. **Run the card's tests.** Every card lists acceptance criteria, hard gates (pass/fail
   conditions), and a primary metric. Run them on real hardware and write down your numbers.
4. **Submit a pull request** that adds **one line to `hall-of-fame/README.md`** reporting:
   - **which model** generated your code,
   - **which platform** it ran on,
   - **which tests passed** (the acceptance criteria and gates),
   - **your measured number** for the card's primary metric.

That's the whole submission. The maintainer reproduces your result on reference-class hardware
and records the champion. **The maintainer scores; you report your numbers** — you don't host or
run any scoring tool here.

To take a belt, clear all of a card's gates and post a better primary-metric number than the
current champion. Bonus respect for offline implementations that drop the cloud dependency.

---

## Writing a new card

Copy `contracts/_TEMPLATE.md` and fill it in. A good card has:

- **Intent** — plain English, one paragraph; the human *why*.
- **Acceptance criteria** — testable and observable, not aspirational.
- **Performance thresholds** — minimum, target, stretch, with one primary metric.
- **Known hard parts (the scars)** — the real ways it has broken, with fixes and tests.
- **Doctrine checks** — how it honors the Care Doctrine.

Then open a pull request. If you write the founding card for an open capability, your name goes
on it.

---

## The two rules that never bend

- **Markdown only. No code, ever.** No program files, no code snippets inside the markdown. The
  promise to readers is that they will never have to read Python or Rust here. The code is a
  *response* a model writes, hosted elsewhere.
- **The Care Doctrine is the floor.** Every card and every implementation honors it. A
  submission that fails the doctrine fails, no matter how good its numbers are.
