# Heirloom Agent Cookbook

> *Agents built to live at home, and to outlive their maker.*

This is a cookbook of tested **recipes** for building real AI devices — and it contains **no
code.** You will never see Python or Rust here. That's the promise. Every recipe is a **Recipe
Card**: a plain-language contract that says what a capability must do, how you know it worked,
how fast it has to be, and what it must never do — with the honest scars from when it broke
before. The code is something a model writes *for you*, hosted in your own project, never in
this repo.

> **New here, and on a computer (no Raspberry Pi)?** The recommended first dish is your own
> **Claude Code Kit** — paste this repo into your coding agent, say *"build my Kit,"* and it
> interviews you and builds a workspace that *remembers you* across sessions. No hardware, ~10
> minutes. Recipe: [`recipes/kit-from-interview.md`](recipes/kit-from-interview.md).

## Why "Heirloom"

An heirloom is something you don't buy — you *inherit.* A thing made with care, kept across
generations, handed down because it's worth keeping. It outlives the person who made it. That's
the first meaning, and it's the promise: these agents are **built to outlive their maker.**

But there's a second meaning, and it's why the name fits all the way down: **heirloom seeds.**
Unlike the patented, locked hybrids that big agriculture sells, an heirloom seed is *open.* It
stays alive only because people keep **growing it, saving it, and sharing it** — passed hand to
hand, getting a little better each season, belonging to no one and everyone. You can't hoard an
heirloom seed. **You keep it by giving it away.**

That is exactly what this cookbook is. Each **recipe is an heirloom seed** — open, with no code
locked inside, kept alive by the community that grows it. The code is just the crop: grown fresh
on your own device, disposable, regrown next season from the same seed. *The recipe endures; the
harvest is yours.* And the one who tends it all is the **Gardener** — because heirlooms aren't
manufactured. They're **grown.**

## Who it's for

People who are not programmers but want to build something real — a warm voice companion for
someone they love, a presence that shows up at three in the morning. If you can read a recipe,
you can build from this cookbook.

## How it works

1. **Read a card** — for example `contracts/R-001-speak.md`, "say one full sentence out loud."
2. **Hand it to an AI** — "build this, honor the doctrine; the acceptance criteria are your tests."
3. **It writes the code.** You run it on a cheap Raspberry Pi.
4. **Meet or beat the champion** — each card has a target number in the Hall of Fame.

**New here? Read this first.** [`essays/from-a-need-to-a-contract.md`](essays/from-a-need-to-a-contract.md)
walks one *real* feature end to end — a caregiver's worry → eight recipe cards → the one that failed
first → durable contracts — with diagrams and no code required. It's the fastest way to see *why* this
works and *when* you'd use it.

## It's a friendly contest

Every Recipe Card is a standing challenge. Build an implementation in any language on any
platform — hosted in *your* repo, never here — pass the card's tests, and submit a one-line
result to the **Hall of Fame** (`hall-of-fame/README.md`): which model you used, which platform,
which tests passed, and your measured number. Clear the gates, beat the current champion, and the
belt is yours. The maintainer scores; you just report your numbers. See `CONTRIBUTING.md`.

## The Care Doctrine is the floor

These companions are for people in the most vulnerable passages of their lives — an elder losing
the present, a child carrying too much. So the cookbook's non-negotiable invariant is moral, not
technical: **never correct their reality; never pretend; the person owns their story; a friend
first.** Read `doctrine/care-doctrine.md` before anything else. A build that's technically
perfect but fails the doctrine fails.

## We're honest about where this sits

We didn't invent the idea that contracts beat code — the research frontier is already proving it.
What's new here is the *combination*: an open community contest, in plain language, where a moral
care invariant is first-class and a beginner can build from it. The full argument (and the honest
caveats) is in `essays/the-code-free-repo.md`.

A reader built his own AI companion in a weekend from cards like these. You can too.

## Start here

Read the Care Doctrine, then read `R-001: Speak`. Pick a card, hand it to an AI, build it on a
$15 board, and come put your name on the board.

**Come build.**

---

*Heirloom Agent Cookbook — created by Stephen Dulaney. Licensed MIT. The recipe stays; the code
is disposable.*
