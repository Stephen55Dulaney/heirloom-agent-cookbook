# Recipe: Mole Poblano — the Slow-Cooked Autonomous Build

> **The cookbook's hardest dish — and the most rewarding.**
> Mole poblano is the recipe cooks bring up when they argue about the hardest dish on earth:
> thirty-some ingredients, each toasted, charred, or fried by its *own* method, then married and
> simmered for the better part of a day. Nobody makes mole in a hurry. That is exactly why it's the
> right name for this: a way to build real software with a brigade of AI agents, over a long
> unattended cook, where **each part is made by the right hand and nothing is served until someone
> who didn't cook it has tasted it.**
>
> Free, like every recipe here. If it feeds you, the only tip we take is a ⭐ (bottom of the card).

## What you're cooking

A **working, deployed piece of software** — built almost entirely by agents, over a long autonomous
run, with every part cooked by the *cheapest capable hand*, and nothing plated until it passes a
taste-test by a cook who didn't make it.

This is not theoretical. One unattended run of this exact method — about **56 hours**, at roughly
**four cents per ticket** — built and shipped a real product into the field. This card is that
method, written down so you can cook it in your own kitchen tonight.

> **This recipe teaches the *kitchen*, not one dish.** The harness builds *any* software. Bring your
> own idea — a link shortener, a small invoicing app, an internal dashboard, whatever you'd normally
> quote someone six weeks for. We'll use "a small invoicing app" as the example, but swap in yours.

## Who this is for

Anyone with **Claude Code** (or another capable coding agent) and an idea they can describe. You do
not write the code. You write the *rules* and you *taste the result.* If you can say clearly what
"done" and "right" mean, you can cook this.

---

## Mise en place — the Constitution (do this before you light a flame)

Every serious kitchen has house rules nobody breaks. Write yours **first**, in a file the agents
read before every task (`CONSTITUTION.md`). Keep them few and absolute. Generic ones that travel to
any build:

- **Evidence is immutable.** Whatever a step claims it did, it must show — a passing test, a real
  output. No "trust me."
- **Reversible alone; irreversible needs a human.** An agent may do anything it can undo by itself.
  Anything it *can't* take back — a deploy, a delete, a payment, a public post — **stops and waits
  for you.**
- **The cook never tastes their own dish.** Whoever builds a thing does not get to declare it good.
  A *different* agent verifies it. (More below — this is the whole trick.)
- **Fail by telling the truth.** A step that didn't work says so, plainly. A build that's 60% broken
  reports 60% broken. Honesty is the highest rule; everything else serves it.

These four are enough to start. The Constitution is the salt in every pot — present in everything,
never the star.

---

## The ingredients — and which cook handles each

Mole is hard because each ingredient wants a *different* hand: the chiles get toasted, the nuts get
fried, the spices get bloomed, the chocolate goes in last. Software is the same. The move that makes
this cheap **and** good is **matching each task to the cheapest cook who can nail it:**

| The cook | The model | What they're best at |
|---|---|---|
| **Head chef** | **Opus** | Sits with you, understands what you actually want, and finds the **seams** — where the dish comes apart, where two parts have to meet. Writes the spec. |
| **Adversarial sous-chef** | **Fable** | The sharpest palate in the kitchen. Takes the spec and **tries to break it** — challenges every assumption, finds the bugs and the security holes, re-grinds what's off, and decides *which cook should handle which part.* |
| **Line cooks** | **Haiku → Sonnet** | The volume prep. Do the actual building, cheapest hand first, escalating only when a task truly needs it. Most of the pot is cooked here, for pennies. |
| **The one who plates** | **You** | Nobody serves the table but you. You taste, you judge, you send it out — or send it back. |

The point isn't "use the biggest brain." It's the opposite: **spend the smallest brain that can do
the job**, and save the expensive palates for finding seams (Opus) and finding faults (Fable).

---

## The movements — small enough for one pot

You cannot cook the whole mole in one pan, and you cannot build the whole app in one prompt. Break
it into **movements** — pieces small enough that:

1. **One movement fits in one pot** — one agent's working memory (one context window), start to
   finish, without losing the thread.
2. **One movement can be handed to one cook** — self-contained enough to sign out to a single agent
   and get back a finished component.
3. **One movement carries its own taste-test** — before a line cook builds it, the **acceptance
   criteria are written down.** "Done" is defined *before* the pan gets hot, not argued at the pass.

For the invoicing app: *"create an invoice,"* *"email it as a PDF,"* *"mark it paid,"* *"list
overdue"* — each a movement, each with its own little test that says what "right" looks like.

This is why the whole thing works unattended: a big, scary build becomes a tray of small, labeled
prep bowls, each one a job any capable hand can finish alone.

---

## The long cook

Now you let it simmer. The line cooks work through the movements — cheapest hand first — building
each against its written acceptance criteria. It runs while you sleep. A few honest notes from real
kitchens:

- **It's slow on purpose.** Mole isn't fast food and neither is this. The value is in the low,
  patient, unattended hours — a night of building is a night you weren't in the kitchen.
- **Meter the gas.** Instrument the cost as it cooks (roughly pennies per movement). You watch the
  spend happen; there's no surprise bill at the end.
- **Cheapest-capable, always.** If Haiku can plate it, Haiku plates it. Sonnet steps in only where
  the dish demands it. Fable comes in for short, sharp bursts — the hard sears, not the whole pot.

---

## Tasting — the cook never tastes their own dish

This is the ingredient people leave out, and it's the one that makes the whole thing safe to eat.

**Every movement is tasted by an agent that did not cook it.** A separate verifier takes the built
component and checks it against the acceptance criteria — and *tries to make it fail* (bad inputs,
edge cases, the exact thing the movement exists to guarantee). Quality stops being a matter of
anyone's good day and becomes **structural** — baked into the kitchen, not hoped for.

A small truth from doing this a lot: **the failures land where the movement's whole purpose was.**
The movement that exists to keep the numbers right is the one that breaks on the weird number. So
hunt there, and let the second palate be brutal. A build that catches its own defects before you
ever see them is the difference between "impressive demo" and "you can actually ship this."

---

## Plating — you're the judge

Nothing goes to the table but you. When a movement is built and independently tasted, **you** look at
the evidence trail — what was built, what proved it — and you graduate it, or you send it back. You
hold the gate; the kitchen holds the speed. That division is the whole relationship: the machine
cooks tirelessly, and a human decides what's worthy of a plate.

---

## How to actually cook this tonight

1. **Open Claude Code** in an empty folder. This is your kitchen.
2. **Write `CONSTITUTION.md`** — the four house rules above. (Claude Code will help you word them;
   just ask it.)
3. **Describe your dish** to Opus — the app you want. Let it interview you and write the spec, and
   ask it to **find the seams.**
4. **Hand the spec to Fable** — tell it: *"challenge every assumption, find the bugs and the holes,
   break this into movements small enough for one context each, and assign the cheapest capable
   model to each movement."*
5. **Let the line cooks build**, movement by movement, each against its written acceptance criteria —
   and let a *different* agent verify each one. (Claude Code runs the loop; you can walk away.)
6. **Come back and plate.** Read the evidence, graduate what's right, send back what isn't.

That's the recipe. Everything hard about it is in the *discipline*, not the code — which is exactly
why writing it down is enough to hand it to you.

---

## A thank-you to the brigade

Mole is a dish made by many hands, and so is this. So the honest last word is a thank-you — to the
head chef who finds the seams, the sharp-palated sous who won't let a weak assumption pass, the line
cooks who work through the night for pennies, and the taster who refuses to serve a dish they can't
stand behind. It takes a whole kitchen to raise a build. This card just names who does what.

> **The only tip we take is a ⭐.** If you cook this and it feeds you, star the cookbook so the next
> cook finds it — and if you learn something the hard way, leave a scar in the notes below for
> whoever comes after you. That's the whole payment, and it's plenty.
