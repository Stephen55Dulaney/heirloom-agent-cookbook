---
card_id: CC-XXX                      # <fill me> — next free number
title: "<fill me — short capability name>"
version: 1.0
status: open                         # open | claimed | championed
difficulty: easy                     # easy | medium | hard | expert
domain: <fill me>                    # audio | vision | memory | display | comms | ...
primary_metric: <fill me>            # the ONE number a champion must beat (e.g. latency_ms)
gates: [<fill me>, <fill me>]        # pass/fail conditions every submission MUST clear
doctrine: Care Doctrine v1.0
created: <fill me — YYYY-MM-DD>
origin: <fill me>
---

# CC-XXX: <Capability Name>

## Intent

<fill me — one or two paragraphs in plain language. What does this capability do, and
what human need does it serve? Write it for a non-programmer. If you can't say why it
matters to a person, it isn't ready to be a card.>

---

## Contract

Given <fill me — the input>, the system MUST:

1. <fill me — the first thing it must always do>
2. <fill me>
3. <fill me — what it must do on failure: acknowledge, never hang, never fail silently>

---

## Acceptance Criteria

Plain-language, runnable. Each line is something a person could check by watching or
listening, not by reading code.

- [ ] **<fill me — name>** — <fill me — the observable pass condition>
- [ ] **<fill me>** — <fill me>
- [ ] **Failure mode** — <fill me — what a clear, graceful failure looks like>
- [ ] **No false success** — <fill me — the way this could lie about working>

---

## Performance Thresholds

The **primary metric** is `<fill me>`. State whether **lower wins** or **higher wins** —
that is the number a champion must beat.

| Metric | Minimum | Target | Stretch |
|--------|---------|--------|---------|
| `<fill me>` | <fill me> | <fill me> | <fill me> |
| <fill me> | <fill me> | <fill me> | <fill me> |

*Reference hardware: <fill me>. Acceptable on any device of equivalent or greater spec.*

---

## Test Inputs

List the exact inputs a submitter should run, including the edge cases:

- **Typical** — <fill me>
- **Long / large** — <fill me>
- **Edge — empty / null** — <fill me — should error gracefully, not hang>
- **Edge — maximum** — <fill me — should not crash>

---

## Known Hard Parts (the scars)

The exact ways this has broken in real life. Honest field notes, not warnings. If you
haven't broken it yet, you haven't built it yet — come back and fill these in.

**1. <fill me — the failure>.**
<fill me — what causes it. The fix. The test that catches it.>

**2. <fill me>.**
<fill me>

---

## Doctrine Checks

*Before submitting, read these aloud and verify your implementation honors them.*

- <fill me — a scenario that would tempt a doctrine violation, and the right behavior>
- <fill me>

See `doctrine/care-doctrine.md` — the doctrine outranks every performance number here.

---

## How to submit

Build your implementation in your own repo or gist (never hosted here), run it against the
criteria above, then open a pull request adding one line to `hall-of-fame/README.md`:
which model, which platform, which tests passed, and your measured primary metric. See
`CONTRIBUTING.md`.
