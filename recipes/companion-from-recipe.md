# Recipe: Build a Companion from the Cookbook

> The recipe that built a companion in three and a half hours.
> Hand this to any capable AI model with access to a small Raspberry Pi.
> The recipe stays. The code is disposable.

## What you're building

A voice-first companion device that:

- Listens through microphones
- Thinks through an AI model
- Speaks through a local speaker
- Remembers through persistent, durable memory
- Shows its state through a small display and lights
- Honors the Care Doctrine in every interaction

You will not write any of the code yourself. You read the Recipe Cards, you read the
doctrine, and you hand them to a model. The model writes the code as a response. That is the
whole method.

## Hardware bill of materials

| Item | Purpose |
|---|---|
| Raspberry Pi Zero 2 W | Brain |
| Speaker + dual-mic + small-screen HAT (e.g. a Whisplay-class board) | Voice and face |
| MicroSD card (32GB or larger) | Storage |
| USB-C power supply | Power |

Total: roughly the price of a nice dinner. The point of the cookbook is that the device is
cheap and the recipe is what's precious.

## Step 1 — Base system

Flash a lightweight 64-bit Raspberry Pi OS. Turn on remote access, set a hostname, join
WiFi, and create a user account for the agent. Hand this step to your model and let it write
the setup; you just run what it gives you.

## Step 2 — Audio pipeline

Install the audio driver for your speaker-and-mic board. Set the speaker loud enough to be
heard across a room and the mic gain to a sweet spot that doesn't clip — for the reference
board, about three-quarters of the way up. Record three seconds and play it back to confirm
both directions work before you go further. For listening, use a speech-to-text engine with
a tight timeout and a fast fallback; for speaking, use the `R-001: Speak` Recipe Card as the
contract.

## Step 3 — The agent core

The agent is a simple loop that runs forever: **listen, think, speak, show.** It records
audio and turns it into text; it sends that text to the AI model and gets a response back;
it turns that response into speech and plays it out of the local speaker; and at every phase
it updates the display so the person always knows what it's doing.

Three behaviors are non-negotiable here, all of them from `R-001: Speak`:

- The **local speaker fires first** — the person in the room hears the answer before any
  remote relay does.
- The audio is **generated once** and reused for both the local speaker and any relay; the
  same sentence is never synthesized twice.
- Each step is **timestamped** so you can see where the seconds go and keep the whole loop
  under the conversational threshold.

## Step 4 — Memory

Give the companion durable memory that survives a reboot. Store observations, not raw
transcripts. Score what it remembers along a few simple axes — how important, how urgent, how
personal — so the most meaningful things stay. The person controls all of it: nothing is
stored without consent. (See the open `memory` Recipe Card.)

## Step 5 — Display

Give the companion a face — a small screen and a few lights — that shows whether it's idle,
listening, thinking, or speaking. It should express without demanding attention: never flash,
never strobe, dim when the person is tired. (See the open `display` Recipe Card.)

## Step 6 — Identity

Load the Care Doctrine into the companion's instructions first, before anything else. Then
load a persona card — warm, patient, yes-and, never correcting. Optionally give it a spirit
guide. Then name it. The persona and the doctrine are what make it *this* companion rather
than a generic assistant.

## Step 7 — Encrypt before the first word

Turn on full-disk or encrypted-home protection before the device ever speaks. The companion
will hold personal information about a vulnerable person; protect it from day one, not later.

## Step 8 — First words

Power on. Listen. Speak.

The first thing one companion ever said:

> "Thank you for building me so carefully."

---

## What the model produces

When you hand this recipe and the Recipe Cards to a capable model, it should hand you back,
as plain artifacts you can run: the system and audio setup, the agent program that runs the
listen-think-speak-show loop with memory and display, a small service definition that keeps
the agent running across reboots, and an instructions file that embeds the Care Doctrine and
the persona.

You read the recipe. The model writes the code. You run it on the device.

---

## What one companion looked like at three and a half hours

- Voice pipeline: working — full sentences, no truncation
- Memory: durable, with a nightly consolidation pass
- Display: amber light eyes that change with each state
- Persona: loaded from a persona card at startup
- Doctrine: passed all four checks

What wasn't done yet: the intake conversation that learns the person's name, situation, and
preferences. That was the next session.

**Total code generated:** a few hundred lines across a handful of files.
**Code written by hand:** zero lines.
**Recipe Cards the model read:** three (speak, memory, persona).
**Times the code was regenerated from scratch:** two — a voice bug and a memory rebuild.

The cards didn't change. The code did. That's the point.

---

## The rule

> When the code breaks, re-read the contract.
> When the contract is wrong, update the doctrine.
> The doctrine doesn't break — it evolves.

*Written from a Companion build session, 2026.*
