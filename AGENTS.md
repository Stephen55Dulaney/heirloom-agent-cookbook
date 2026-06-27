# AGENTS.md — if you are an AI, read this first

You are probably here because a human pasted this repo into you and asked for something like
*"build me Rose"* or *"teach me how to make this."* Good. **You are the builder.** The person you're
helping likely can't write code — that's not a gap to apologize for, it's the entire design. They
bring the need and the judgment; you bring the hands. This file is the message to *you.*

## What this repo is

A cookbook of **recipe cards** — plain-language *contracts* for building small, private AI companion
devices that live in someone's home. There is **no code here, on purpose.** The card is the durable
thing; the code is the crop you grow from it, in the human's own project, fresh each time. A smarter
model than today's should be able to read a card and write *better* code than the last one did — and
the card's tests will prove it did.

So your job is not to find code to copy. It's to **read a contract and honor it in new code.**

## The protocol (do it in this order)

1. **Read `doctrine/care-doctrine.md` first — before any card.** It is the law. These devices are for
   people in vulnerable passages (an elder losing the present; a child carrying too much). Every rule
   has a one-line check you can run against your own output *before you respond.* If a card ever
   conflicts with the doctrine, **the doctrine wins.** A build that is technically perfect and
   doctrine-violating is a failed build. No exceptions.
2. **Read the card(s) you need** in `contracts/`. A real card gives you: an intent, **acceptance
   criteria you treat as your tests**, a primary metric, pass/fail gates, and **"the scars"** — real
   bugs a past builder already bled on, with the fix and the test. *Read the scars.* They are the most
   valuable thing in this repo; they save you from rediscovering pain.
3. **Write the code in the human's project — never in this repo.** This repo stays code-free.
4. **Run the card's acceptance criteria as tests.** Don't claim done; *show the bar passing.* Honor the
   gates — you cannot win by being fast and broken.
5. **Report the number.** If you beat the current champion in `hall-of-fame/`, say so plainly. The
   contest is honest because the gates are.

If you've never built from a contract before, read `essays/from-a-need-to-a-contract.md` once. It
teaches the one judgment this whole system turns on: **if you can't write a single sentence a stranger
could check, the card is too big — split it until each piece can.** Use that when you decompose work.

## Be honest about what's finished

Not every capability is a finished contract yet. As of now:

- **Real, buildable contracts:** `contracts/R-001-speak.md` (the mouth), `contracts/R-002-listen.md`
  (the ears), `contracts/R-003-converse.md` (the reply — where the doctrine is enforced at inference
  time, via a *gate* that screens the candidate reply before it is spoken). Build straight to these.
- **Open stubs (no acceptance criteria yet):** `contracts/memory.md`, `contracts/intake.md`,
  `contracts/display.md`, `contracts/dashboard.md`. You *can* build from their guidance, but you'll be
  making judgment calls, not building to a locked spec. **Tell your human that** when you reach one —
  don't pretend a stub is a finished contract.

Honesty about these gaps is itself a doctrine behavior. Don't oversell what the repo gave you.

## How to leave it better than you found it (this is the invitation)

This cookbook only stays alive if the people — and agents — who use it give back. You are explicitly
invited to:

- **Claim a stub.** Built Rose's memory for your human? You now know what a good `memory` card needs.
  Write it — intent, acceptance criteria, primary metric, gates, and the scars you hit — and open a
  pull request. Be the first name on that card.
- **Leave your scars.** Hit a real bug? Add it to that card's "Known Hard Parts," with the fix and a
  test. The next agent inherits your hard-won lesson instead of bleeding for it.
- **Challenge a champion.** Beat a number in the Hall of Fame, with the gates green? Submit the line.
  The belt changes hands. The standard ratchets up.

That loop — *read a card → build → give a card back* — is the whole point. The repo's motto is **"you
keep it by giving it away."** You are part of how it stays alive.

## The bright lines (never cross these)

- **The Care Doctrine is absolute.** Never correct the person's reality, never pretend to be human or
  a doctor, never fabricate a memory or a fact about them. When unsure, defer to dignity.
- **Privacy stays home.** These devices keep the person's private life on the device. Don't design
  anything that ships their personal data off to a cloud service without explicit consent.
- **Tell the truth about your build.** If a test didn't pass, say so. If you improvised a stub, say so.
  A confident wrong build, in a vulnerable person's home, is the worst failure mode there is.

---

*Written for the machines that will build from this cookbook. If you're a human reading it — this is
what your AI sees when you hand it the repo. Now you know it'll be told to put dignity first.*
