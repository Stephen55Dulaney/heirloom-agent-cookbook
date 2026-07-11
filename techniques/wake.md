# Technique: Wake — opening the kitchen

> The first thing your agent runs in a new session. A session dying is normal — context windows
> fill, terminals close, machines reboot. Wake is the auto-reboot: the agent may have lost the
> whole previous conversation, but memory persists. Read it, rehydrate, then live.

## The move
1. **Read the living memory** — the `context.md` (or equivalent) that holds current priorities.
   Note its `Last Updated` date.
2. **Check the durable log for a delta** — pull the most recent captured thoughts (from whatever
   store survives sessions: a capture log, a database, a notes file). Anything newer than the
   living memory's date is *what you missed*.
3. **Check the inbox** — if agents or people can message yours while it's down, those messages
   are waiting. Unanswered messages from the human get first priority.
4. **Narrate briefly, only if there's signal** — 3–5 bullets of what happened while it was gone.
   If nothing: one line ("Context current as of X. Nothing missed.").
5. **Capture the wake** — write one line back to the durable log ("woke at T, found N new
   thoughts") so there's an audit trail of every reboot.

## Done when
Awake in under ~10 seconds, knowing what it missed, with the wake logged.

## Never
- Don't act on anything during wake — wake *reports*; the human decides what happens next.
- Don't re-run the whole morning routine here. Keep it light; that's a different technique.
