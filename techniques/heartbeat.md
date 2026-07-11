# Technique: Heartbeat — watching the stove

> A cheap, recurring pulse the agent runs through the working day (every ~15 minutes is a good
> default). Its job is to keep an eye on the few things the agent owns and surface ONLY what's
> new or broken. Default to silence.

## The move
1. **Look ahead, don't just look around.** The highest-value check is the calendar: is anything
   imminent (~20 min out)? If yes, escalate loudly — title, time, the join link. Everything else
   is quiet.
2. **One cheap status check** for the infrastructure the agent owns (inboxes, bridges, services).
   Make it a single pre-approved command so the pulse runs unattended.
3. **Report in one line** when nothing changed: `Quiet. Next: <thing> in <N>m. (HH:MM)`.
4. **Surface, don't solve.** Something new gets max ~4 bullets and stops. No decisions that
   aren't trivially reversible.

## Tuning (the honest scar)
A month of 5-minute pulses showed the routine inbox checks hit ~0% — the ONE thing that ever
mattered was a meeting reminder. So: point the spend at look-ahead, loosen the cadence, and
tighten only when something is actually imminent. The pulse earns its cost through the one save
a week, not the hundred quiet ticks.

## Never
- Never let the heartbeat become a second workday. It watches; it doesn't cook.
