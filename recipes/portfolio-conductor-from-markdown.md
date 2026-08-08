# Recipe: A Portfolio Conductor from a Folder of Projects

> For the builder with too many pots on the stove. You have ten, thirty, sixty projects —
> half asleep, some burning, and every morning starts with the same expensive question:
> *where was I?* This dish turns that thirty-minute question into a five-minute briefing,
> using nothing but small markdown files, git, and an agent that reads both. The reference
> build ran a 60+ project portfolio for over a year.

## What you're building

A **conductor**: an agent practice that watches every project you have and tells you, each
morning, what deserves your attention — grounded in evidence, not anxiety. It is not a
dashboard you maintain. Dashboards rot the day you stop feeding them. The conductor feeds
itself, because of one idea:

**Projects self-report through small files, and version history tells the truth about the
rest.** Everything else is derived.

## The shape (three layers, built in order)

### Layer 1 — Four small files per project

Ask your agent to establish a convention: any project may carry

- **a status file** — current phase, percent done, blockers, next actions, last-updated date;
- **an assumptions file** — each assumption marked validated / testing / untested / invalidated;
- **a dependencies file** — what this needs, what needs it;
- **a learnings file** — dated, hard-won patterns (see the
  [`learnings-ledger`](../techniques/learnings-ledger.md) technique).

Projects without the files still participate — their activity history speaks for them. The
files are an invitation, not a tax.

### Layer 2 — The scanner

Have your agent write (in your own repo, never here) a scanner that walks your projects folder
and produces one dated snapshot: per project, the parsed four files, the version-history facts
(last change, when, uncommitted work?), and a rough **health score** — points for each file
present, points for recent activity. The score's job is *ranking your attention*, not judging
your worth. Keep every snapshot; the stack of them is your portfolio's history for free.

### Layer 3 — The agents (start with two)

Each "agent" is just a written procedure your coding agent follows — a technique card, not a
program:

- **The Arbiter** (daily) — reads the newest snapshot and yesterday's
  [`ambition-close`](../techniques/ambition-close.md), then plans today *with* you, in
  conversation.
- **The Conductor** (weekly) — the full-orchestra review: reads everything, surfaces the three
  projects that need a decision, the assumptions that have sat untested longest, and the
  learnings that should travel from one project to another.

The reference build eventually grew nine specialists (a skeptic that designs tests for stale
assumptions, a blocker-hunter, a duplicate-effort spotter, a meeting-prep briefer…). **Do not
start with nine.** Add a specialist only when a real, recurring pain calls for it. A conductor
with more agents than you have attention is just a noisier dashboard.

## The daily rhythm that powers it

The conductor is the *where*; the [seven daily techniques](../techniques/README.md) are the
*when*: wake → ambition → work (+ heartbeat) → ambition-close → reflect → dream → sleep. The
snapshot feeds the morning plan; the day's real diffs feed the evening reckoning; the
reckonings feed the learnings ledger; the ledger feeds every future plan. That loop is the
whole machine. Break any link and the rest becomes decoration.

## Acceptance Criteria (how you know it works)

- [ ] **The scan is cheap** — one command over 20+ projects yields a ranked snapshot in under
      a minute.
- [ ] **Morning is grounded** — the day's plan cites yesterday's evidence, not vibes.
- [ ] **Evening is honest** — the close grades the plan from actual changes, and a MISS is
      written as a MISS.
- [ ] **Learnings travel** — a lesson recorded in one project surfaces when it applies to
      another.
- [ ] **Nothing to feed** — you can ignore the whole system for two weeks, come back, run one
      scan, and be current. (This is the test dashboards fail.)

## Primary metric (for the Hall of Fame)

`minutes_to_oriented` — from sitting down cold to knowing your top three priorities with
evidence. **Lower wins.** Reference build: under 5 minutes, from a former 30+.

## Known Hard Parts (the scars)

**1. Change messages lie; changes don't.** Every summary a human (or agent) writes about work
is opinion. Grade days and attribute effort from the actual diffs. The whole reference
architecture came from a colleague's remark: *"just compare the two codes."*

**2. The recommendation loop opens silently.** The close writes advice; the value only exists
if tomorrow's plan *reads* it. Wire that handoff mechanically. Following it once flipped a 33%
completion day to 86%.

**3. Carried items rot.** Anything carried two-plus weeks untouched gets a binary
commit-or-drop with a written reason. No third option — "carry again" is how backlogs
metastasize.

**4. A zero health score doesn't mean a dead project.** It means "not self-reporting." The
scanner surfaces; the human decides. Some of the most personal work never fills in a status
file.

**5. Anything with a person's name on it deserves extra scrutiny.** When the conductor
proposes cleanup, resources named after real people get surfaced for a human decision even if
they look unused. Paranoid preservation costs nothing; breaking a named pipeline costs trust.

## Doctrine Checks

- The conductor reports; **the human decides.** No agent in this dish takes destructive action
  on a project without a confirmation gate.
- **Never fake the health.** A project the scanner can't read is reported as unreadable — not
  scored, not guessed.

## Leave it better

Built one? The scars worth sending back: what your health score missed, the specialist agent
that actually earned its seat, and how long your snapshot history got before it told you
something you didn't know about yourself.

---

*The orchestra was never the problem. The problem was that nobody was listening to all of it
at once. The conductor is just the listening, made cheap enough to do every day.*
