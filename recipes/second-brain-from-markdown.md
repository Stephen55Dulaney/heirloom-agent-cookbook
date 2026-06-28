# Recipe: A Second Brain from a Folder of Markdown

> Turn the pile of notes you already have into a knowledge base that an AI keeps current for you —
> the way a good librarian would, if the librarian never slept and never lost a card.

## What you're building

You have notes. Maybe hundreds of them — meeting notes, things you read, ideas you typed at midnight.
The problem was never *writing* them. It was *keeping them useful*: cross-referencing, summarizing,
remembering which note said what. That bookkeeping is the chore no human keeps up with.

This recipe builds a **self-maintaining wiki**: you drop raw notes into one folder, and an AI reads them,
writes tidy summary pages into a second folder, keeps a one-line index of everything, and — periodically —
checks its own work for contradictions and stale claims. You end up with a knowledge base that *compounds*
instead of rotting. No coding. You talk to an AI (Claude Code, Codex, or similar); it does the filing.

This is the pattern Andrej Karpathy named the *"LLM Wiki,"* built the way a home companion actually runs it.

## The shape (three folders + a rulebook)

Tell your AI to set up four things:

- **`raw/`** — where your source notes live. **Immutable.** The AI reads from here but never edits it.
  This is your ground truth. Drop anything in: notes, articles, transcripts.
- **`wiki/`** — where the AI writes. One markdown page per *concept* (a person, a project, an idea), each
  a clean synthesis of what the raw notes say about it. You read these. The AI owns them.
- **`index.md`** — the table of contents: **one line per wiki page**, each with a one-sentence summary.
  This is what makes the whole base scannable at a glance. Keep it lean — one line, always.
- **`AGENTS.md`** (or `CLAUDE.md`) — the rulebook that turns a generic AI into a disciplined librarian:
  how pages are structured, how a new note gets filed, how answers get written.

## The three things you'll ask it to do

**1. Ingest** — *"Read the new notes in `raw/` and update the wiki."*
The AI reads each new source, tells you the key takeaways, writes or updates the relevant `wiki/` pages,
adds backlinks between related pages, and updates `index.md`. One note often touches several pages.

**2. Query** — *"What do my notes say about X?"*
The AI searches the `wiki/`, reads the relevant pages, and answers **with citations** back to the source.
Because the knowledge is already synthesized, it isn't re-reading everything from scratch each time.

**3. Lint** — *"Health-check the wiki."*
Periodically, ask it to hunt for contradictions between pages, stale claims a newer note has overtaken, and
orphan pages nothing links to. This is the step everyone skips and the step that keeps the base honest.

> The read-at-start / write-at-end rhythm is the heart of it: at the start of a work session the AI reads
> the index to remember where things are; at the end it files what's new. (In the Genesis household this is
> literally a `/wake` in the morning and a `/reflect` + `/dream` at night.)

## Acceptance Criteria (how you know it works)

- [ ] **Ingest works** — Drop a new note in `raw/`. Ask the AI to ingest. A `wiki/` page is created or
  updated, and `index.md` gains/updates its one-line entry.
- [ ] **The index stays scannable** — Every line in `index.md` is a link + a one-sentence summary. Nothing
  longer. You can read the whole index in under a minute.
- [ ] **Query cites its sources** — Ask a question; the answer points back to the raw note(s) it came from.
- [ ] **Synthesis, not copying** — A `wiki/` page reads like a clean summary of a topic, not a pasted dump
  of the raw note.
- [ ] **Lint catches something real** — Run a lint pass on a base with a deliberate contradiction (say two
  notes that disagree). The AI flags it rather than silently keeping both.
- [ ] **`raw/` is untouched** — After many ingests, your original notes are byte-for-byte unchanged.

## Primary metric (for the Hall of Fame)

`index_scannable` — can a stranger understand the whole base from `index.md` alone in under 60 seconds?
**Yes wins.** (A base whose index has bloated past scannable has failed the one job the index has — this is
the most common way these systems rot.)

## The bright lines (never cross)

- **`raw/` is immutable.** The AI reads it, never edits it. Your ground truth must stay ground truth.
- **The index stays one-line-per-page.** The moment entries grow into paragraphs, the base stops being
  scannable and starts being a second pile. Detail goes in the wiki page; the index just points.
- **No invented knowledge.** A wiki page may only contain what the raw notes support, with citations. If
  the notes don't say it, the wiki doesn't claim it. (If this base holds anything about a real person's
  health or private life, keep it local and anonymized — see `doctrine/care-doctrine.md`.)
- **Synthesize honestly.** When two notes disagree, the lint surfaces it for *you* to resolve — the AI
  doesn't quietly pick a winner.

## Leave it better (the invitation)

Built one? Tell us what broke. The scars worth sending back: how big your `raw/` got before the index
needed pruning; whether the AI started inventing cross-links that weren't real; what your lint pass caught
that you'd have missed. The card that needs your scars most is `contracts/memory.md` — this recipe is its
do-it-yourself cousin.

---

*The bottleneck was never the reading or the thinking. It was the filing. Hand the filing to something that
never tires, keep the index lean, and let it lint itself honest — and the pile of notes you already have
becomes a brain that grows.*
