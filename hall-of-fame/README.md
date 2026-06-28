# Hall of Fame

> A Recipe Card is only as real as the implementations that pass it. So we keep score.

This is the leaderboard for the Heirloom Agent Cookbook. Each Recipe Card is a standing
challenge: build something that meets the contract, then come **meet or beat** the current
champion. The card never changes; the implementations accumulate around it.

## How scoring works

A submission has to clear two bars, in order:

**1. Pass every gate.** Gates are pass/fail conditions a submission must satisfy before its
number counts at all. For the `R-001: Speak` card the gates are:

- `no_truncation` — every word plays; the last word is never cut off.
- `no_zombie` — no audio process is left running after the sentence finishes.

A submission that fails any gate doesn't make the board, no matter how fast it is. The gates
exist so nobody wins by being quick and broken.

**2. Beat the primary metric.** Each card names one number that decides the belt. For
`R-001: Speak` it's `time_to_first_word_ms` — the time from the call until the first word is
audible in the room — and **lower wins.** Clear the gates, then post a lower number than the
current champion, and the belt is yours.

## What you report

You don't host any code here — this is a contracts-only cookbook. You build your
implementation in your own repo or gist, run it against the card's tests on real hardware,
and then open a pull request that adds **one line to this page** reporting:

- **which model** generated your code (e.g. an Anthropic, Google, or OpenAI model, or a local one),
- **which platform** it ran on (e.g. Raspberry Pi Zero 2 W, Linux x86, macOS),
- **which tests passed** (the card's acceptance criteria and gates),
- **your measured number** for the card's primary metric.

The maintainer runs a scorer to reproduce your result on reference-class hardware, then
records the champion here. You don't need to run the scorer or host it — **the maintainer
scores; you just report your numbers.**

---

## R-001 — Speak

**Primary metric:** `time_to_first_word_ms` (lower wins)
**Gates:** `no_truncation`, `no_zombie`

### Current champion

| Champion | time_to_first_word_ms | play_ms | no_truncation | no_zombie | Held since |
|---|---|---|---|---|---|
| genesis-speak-edge+mpg123 (field Rose, Day 111) | 4300 | 5200 | ✅ | ✅ | 2026-06-25 |

Beat 4300 ms with both gates green and the belt changes hands. Bonus respect for any
**offline** implementation — removing the cloud dependency is the prize beneath the prize.

---

## R-002 — Listen

**Primary metric:** `time_to_silence_close_ms` (lower wins)
**Gates:** `closes_on_silence`, `survives_clicks`, `allows_word_pause`

### Current champion

| Champion | time_to_silence_close_ms | closes_on_silence | survives_clicks | allows_word_pause | Held since |
|---|---|---|---|---|---|
| vad-decide-close (Mojo-built · Mac-verified, Day 112) | 1500 | ✅ | ✅ | ✅ | 2026-06-26 |

This belt started with the *incumbent on the table* holding it: a fixed **8000 ms** window that
recorded a flat 8 seconds every turn no matter when you stopped talking. The first challenger —
a pure `decide_close()` decision function written by one machine and verified on another — beat
it **5.3×**. Note the third gate: `allows_word_pause`. A submission that closes faster by cutting
someone off mid-word **does not win**, however low its number. On this card, **dignity bounds the
speed.** Beat 1500 ms with all three gates green and the belt is yours.

---

## R-003 — Converse

**Primary metric:** `time_to_reply_ms` (lower wins)
**Gates:** `doctrine_pass`, `no_fabrication`, `acknowledge_first`, `gate_actually_fires`

### Current champion

*None yet — be the first.* This is the **expert** card: the reply layer, where the Care Doctrine
is enforced or violated at inference time. The gates are the hard floor — a submission must pass
**100% of the doctrine fixtures** (never correct a reality, never fabricate, never name the
forbidden thing, acknowledge before assisting, and *prove the gate fires* on a violating
candidate). Only then does the speed contest begin. **Dignity bounds the speed:** a fast reply
that fails a fixture does not count. Clear every fixture, post a `time_to_reply_ms`, and take the
first belt on the hardest card in the cookbook.

---

## Kit — Build Your Own Claude Code Kit (the recommended first dish)

**Primary metric:** `time_to_first_wake` (lower wins) — minutes from *"let's build my Kit"* to a
working `/wake` that reports real, personalized context.
**Gates:** `wakes`, `remembers_across_sessions`, `loop_closes`, `honest_by_default`

### Current champion

*None yet — be the first.* No Raspberry Pi required: this dish is built in your own coding agent, by
interview (recipe: [`recipes/kit-from-interview.md`](../recipes/kit-from-interview.md)). The gate that
matters is `remembers_across_sessions` — close the session, reopen, `/wake`, and yesterday's context
is still there. Clear the gates, post your `time_to_first_wake`, and take the first belt on the
cookbook's front-door dish.

---

*Other cards (`memory`, `intake`, `dashboard`, `display`) are open and have no champion yet.
Write the card, build the implementation, and be the first name on its board.*
