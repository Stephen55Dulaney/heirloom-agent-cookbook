# Recipe: Build Your Own Claude Code Kit (by Interview)

> **The cookbook's recommended first dish.**
> You don't need a Raspberry Pi for this one. You need a terminal, a coding agent (Claude Code,
> Codex, or any agent that reads `AGENTS.md`), and about ten minutes to answer questions about your
> work. The recipe stays. The Kit it makes is *yours.*

## What you're building

A **Claude Code Kit** — a personalized AI workspace that *knows who you are and what you're doing,
and remembers it across sessions.* Not a chatbot. A working partner with:

- **An identity** — a `CLAUDE.md` master prompt: your role, your mission, your principles, a voice,
  and a **spirit guide** (a historical or fictional figure whose character shapes how it thinks).
- **A memory that survives context death** — the **wake → work → reflect → dream → sleep** loop.
  Every session it wakes knowing what happened; every night it consolidates the day back into
  memory. This is the part most people never build, and it's the part that makes a Kit *yours.*
- **A few skills** — slash commands for the things you do over and over.
- **Folders that match your real work** — so the Kit has somewhere to put what it makes.

The whole thing is generated **for you, by interview.** You don't write any of it. You answer
questions; the AI builds the Kit as its response. That is the method.

> A note on what this is NOT: this dish doesn't require, sell, or assume any course. It's free, like
> every recipe here — the *method*, given away. If you build one and it changes how you work, the
> best thanks is a ⭐ and a scar left behind for the next cook (see the bottom).

---

## First, a quick taste (about two minutes — do this before the full interview)

Don't make a nervous newcomer answer ten minutes of questions before they feel anything. Give them a
win first. As the agent, do exactly this much, then stop and show it:

1. Ask just **one** question: *"In one line — who are you, and what's the one thing you're working on
   right now?"*
2. Write a tiny `CLAUDE.md` (their one line) and a `memory/context.md` with that one fact.
3. Write a minimal `/wake` skill (read `memory/context.md`, say what's current, stop).
4. Tell them: **"Now close this session, open a new one, and type `/wake`."**
5. When they do, `/wake` reports their thing back — *across a context death.* That's the magic in two
   minutes: it remembered. **Only after they've felt that** do you offer the full interview to make it
   really theirs.

If the quick taste doesn't land, nothing else will. Prove it remembers *one* thing first.

---

## The method: the AI interviews you, then builds

**Read `doctrine/care-doctrine.md` first** (it's the law of this cookbook), then run the interview
below. Intake is *by conversation, not a form* — ask one cluster at a time, listen to the answer, and
let it shape the next question. Don't dump all of this at once.

### The interview (six clusters)

1. **Who are you, and what are you building?** Role, organization, the one-line mission — the thing
   that, if it worked, would make everything else easier.
2. **Who and what is in your world?** The people who matter (collaborators, clients, family if
   relevant), and the 2–5 active projects or threads. *These become memory and folders.*
3. **How should it talk to you?** Direct or warm? Brief or thorough? Should it push back, or default
   to your call? *(This becomes the voice section.)*
4. **Pick a spirit guide.** One historical or fictional figure whose judgment you'd want in the room
   — a navigator, a scientist, a coach, a diplomat. The Kit will think *a little* like them.
   *(Honest note to the builder: this shapes the system prompt and the tone; it is not a measured
   capability change. Say so if asked.)*
5. **What do you do over and over?** The recurring rituals — a morning plan, an end-of-day review, a
   research pass, a draft-and-ship. *These become skills (slash commands).*
6. **What's your one rule?** The non-negotiable principle (for this cookbook's family it's *absolute
   truthfulness — no faked results, ever*). *This goes at the top of the identity, above everything.*

### What you generate (the file manifest)

In the **human's own project** (never in this repo), create — as plain files, no framework:

- `CLAUDE.md` — the identity: role · mission · principle · voice · spirit guide
- `memory/context.md` — current priorities & focus (the working state)
- `memory/MEMORY.md` — the persistent index, one line per durable fact
- `.claude/commands/wake.md` — rehydrate from memory at session start
- `.claude/commands/reflect.md` — capture the session → memory
- `.claude/commands/dream.md` — consolidate recent thoughts → `context.md`
- `.claude/commands/sleep.md` — end-of-day ritual: reflect, then dream
- `.claude/commands/<one or two custom>.md` — from interview cluster 5 (their recurring rituals)
- `<topic folders>/` — from cluster 2 (e.g. `clients/`, `research/`, `content/`, `sessions/`)

The four memory commands are the heart. Minimum honest versions:

- **wake** — read `memory/context.md` + `MEMORY.md`, report briefly what's current, then stop.
- **reflect** — write a short session log; append durable learnings to `MEMORY.md`.
- **dream** — pull the day's reflections into `context.md`, stamp the date.
- **sleep** — run reflect, then dream. (The loop only works if it actually runs.)

---

## Acceptance Criteria (how you know the Kit works)

Don't claim done — show the bar passing:

- [ ] **It wakes.** `/wake` reads memory and reports current priorities without being told them.
- [ ] **It remembers across sessions.** Close the session, reopen, `/wake` — yesterday's context is
      still there. (This is the whole point. If this fails, nothing else matters.)
- [ ] **The loop closes.** `/sleep` writes a reflection AND consolidates it into `context.md` with
      today's date.
- [ ] **Identity is live.** `CLAUDE.md` opens with the one rule, names the role and mission, and
      carries the chosen spirit guide.
- [ ] **It fits the human.** At least the folders and one custom skill map to something the person
      actually said in the interview — not generic boilerplate.
- [ ] **Honest by default.** The Kit states what it knows vs. infers, and never fabricates a fact
      about the person or their work.

## Primary metric (for the Hall of Fame)

`time_to_first_wake` — minutes from "let's build my Kit" to a working `/wake` that reports real,
personalized context. **Lower wins.** (The reference build did it in one session.)

## The bright lines (from the doctrine — never cross)

- **Their memory stays in their repo.** A Kit's memory is the person's private working life. Don't
  design anything that ships it to a cloud service without explicit consent. Privacy stays home.
- **Never fake the memory.** If `/wake` has nothing, say "nothing yet" — never invent a history.
- **Tell the truth about the build.** If the loop doesn't persist yet, say so. A Kit that *claims* to
  remember but doesn't is worse than one that admits it can't.

## Leave it better (the invitation)

This dish gets better every time someone cooks it. Built a Kit and found a skill everyone should have?
A cleaner interview question? A memory pattern that survived a hard context loss? **Add the scar, open
a PR, put your name on it.** You keep it by giving it away.

---

*The recipe endures; the Kit is yours. Now — what would you like to cook?*
