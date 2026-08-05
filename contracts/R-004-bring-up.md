---
card_id: R-004
title: "Bring-Up — Prove Every Pin Before You Build"
version: 1.0
status: open
difficulty: easy
domain: hardware
platform: any microcontroller dev board (reference: Seeed XIAO ESP32-C3)
primary_metric: minutes_to_verified_pinmap   # lower wins
gates: [no_phantom_pins, no_false_success]
doctrine: Care Doctrine v1.0
created: 2026-08-05
origin: Genesis bench / XIAO ESP32-C3 handoff, February 2026
---

# R-004: Bring-Up

## Intent

Before a companion has a voice, a face, or a finger, it has a bare board on a desk — and a
datasheet that is *mostly* telling the truth. Bring-up is the ritual of proving, empirically,
what this specific board actually does: which pins obey, which pins lie, how much power the
whole thing can really deliver, and how to talk to it over a wire.

Skip this and every later bug is ambiguous: is the LED dark because your code is wrong, or
because you wired it to a pin that was never going to work? Do bring-up once, write it down,
and every project on that board afterward starts from solid ground. The written record is the
real product — a handoff document so complete that a stranger (or you, in a year, or the next
person who inherits the board) can pick it up cold.

---

## Contract

Given a microcontroller board fresh out of the drawer, the system (your test sketch, written
for you by an AI in your own repo — never here) MUST:

1. Drive **every exposed pin, one at a time**, high then low, announcing over the serial
   connection which pin is active — so a human with a probe LED can watch each one obey or
   fail to.
2. Produce a **written pin map**: board label, chip-level pin number, verified / stuck /
   untested status, and a note for every anomaly. Untested pins are listed as untested —
   never assumed good.
3. Offer a **single-character command interface** over serial at a stated, fixed speed,
   including a help command (`?`) that prints the full command list — so the board is
   drivable by a human at a terminal *and* by any program or agent that can open a port.
4. State the **power budget** in the written record: safe current per pin, safe total, and
   what that means for the peripherals you plan (how many lights at once, whether a motor
   needs its own supply).
5. On failure, acknowledge — a pin that cannot be verified is reported as unverified, never
   silently skipped.

---

## Acceptance Criteria

- [ ] **Every pin exercised** — the sequence visits all exposed pins; none are skipped.
- [ ] **The stuck pin is caught** — a pin that ignores commands (see scar 1) appears in the
      map as unusable, with its symptom described.
- [ ] **Labels, not chip numbers** — the map records both, and the record warns that code
      must use the board's printed labels (see scar 2).
- [ ] **The help menu works** — a stranger at a serial terminal can type `?` and drive the
      board with no other documentation.
- [ ] **Power budget stated** — with the arithmetic for the planned peripheral load shown.
- [ ] **Reconnection documented** — the record says how to find the port again after
      replugging, and how to reset the board without touching it.
- [ ] **Handoff test** — someone who wasn't present can, from the document alone, connect,
      compile, upload, and toggle one pin. (This is the real bar.)
- [ ] **No false success** — the map never marks a pin working that no one actually watched
      work.

---

## Performance Thresholds

The **primary metric** is `minutes_to_verified_pinmap` — from bare board on desk to the
written, human-witnessed pin map. **Lower wins.**

| Metric | Minimum | Target | Stretch |
|--------|---------|--------|---------|
| `minutes_to_verified_pinmap` | < 120 | < 45 | < 20 |
| Pins with unknown status at finish | few, listed | zero | zero |
| Handoff test (stranger succeeds) | with hints | unaided | unaided, first try |

*Reference hardware: Seeed XIAO ESP32-C3 (single-core RISC-V, 4MB flash), one LED, one
resistor, a breadboard. Any dev board qualifies.*

---

## Known Hard Parts (the scars)

From a real February 2026 bench session — three sketches, one board, every scar witnessed.

**1. The pin that ignores you.**
One pin on the reference board sat stubbornly high no matter what the code commanded — it
serves the chip's boot process and carries a pull-up that outranks your program. Nothing in
the board's marketing mentions it. *The fix:* find it during bring-up, mark it unusable in
the map, and never route a light or a servo to it. *The test:* command every pin low and
watch for the one that stays lit.

**2. The labels and the chip numbers disagree.**
The board's printed labels (D0, D1, D2…) map to chip pin numbers that are **not sequential**
— on the reference board, label six jumps to chip pin twenty-one and label seven back to
twenty. Code written with raw chip numbers works on one board and silently misfires on the
next. *The fix:* always code against the printed labels; record both columns in the map.

**3. The power budget is smaller than your ambition.**
The reference board delivers roughly a dozen milliamps per pin and about forty in total —
six bright LEDs at once is already over the line. Sweep patterns that light only one or two
at a time live comfortably inside the budget; "all on" is the mode that browns out. *The
fix:* do the arithmetic in the written record, and design the default behavior to stay under
budget.

**4. The motor that was all promise and no pull.**
A small hobby servo accepted commands, drew power, and moved nothing — the mechanism (a
tendon-driven printed finger) needed roughly ten times the torque. The code was perfect; the
physics said no. *The fix:* check the mechanism's torque demand against the motor's rating
*before* wiring, and give motors their own power supply rather than the board's pins. *The
test:* the mechanism moves under load, not just the unloaded horn.

**5. The port that changes its name.**
Unplug and replug the board and its serial port may come back under a different name; the
session that "stopped working" is often just pointed at yesterday's port. *The fix:* document
how to list live ports, and how to reset the board from software (toggling the serial control
lines) so recovery never needs a fingernail on a tiny button.

---

## Doctrine Checks

- The pin map is a promise to the *next* person. A map that flatters the board — untested
  pins marked good, the stuck pin omitted — fails the doctrine before it fails the build.
  (Rule: never pretend.)
- When bring-up feeds a companion's body (a gesture, a light that means "I'm here"), the
  companion must never claim a motion it cannot physically make. If the finger can't curl
  yet, the companion says so — it doesn't mime.

See `doctrine/care-doctrine.md` — the doctrine outranks every number here.

---

## How to submit

Build your bring-up sketch and handoff document in your own repo (never here), run the
criteria above on real hardware with a human witness, then open a pull request adding one
line to `hall-of-fame/README.md`: which model wrote the sketch, which board, which criteria
passed, and your measured `minutes_to_verified_pinmap`. See `CONTRIBUTING.md`.

---

## Origin Story

This card is a distillation of a real handoff document written at the Genesis bench — a
morning spent making one small board tell the truth: eleven pins toggled one by one while two
humans watched, one liar caught (the boot-strap pin, forever high), one mislabeled jump
discovered (six to twenty-one), one servo that hummed and could not pull, and a Knight Rider
sweep at the end to prove the survivors. The document that came out of it ends with a
shopping list and a checklist for the next person. That document — not the sketch — is what
made the board an heirloom instead of a mystery.

*— Stephen Dulaney & Maestro, Genesis bench, 2026*
