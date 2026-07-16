# Stage 3: The Command Deck

## The Story

The outpost has more than sensors — it has subsystems: lights, doors,
pumps, alarms. Real control systems don't give each one its own giant
variable; they pack them into a single status word, one bit per
subsystem, exactly like real hardware registers do. Time to build the
command deck.

---

## Missions

**Mission 3.1 — Define the Subsystems**
Assign each subsystem a bit position (e.g. `LIGHTS = 1<<0`,
`DOORS = 1<<1`, `PUMPS = 1<<2`, `ALARM = 1<<3`) in a single
`uint8_t status_word`.
*(skills: bitwise operators, `<stdint.h>` fixed-width types)*

**Mission 3.2 — Turn Things On and Off**
Write functions to turn a subsystem ON (`|=`), OFF (`&= ~`), and
TOGGLE (`^=`) within the status word.
*(skills: `|`, `&`, `~`, `^`, `<<`)*

**Mission 3.3 — Read the Deck**
Print the status word in binary so you can *see* which bits are set.
*(skills: bit-shifting and masking to extract individual bits)*

**Mission 3.4 — Simulate an Incoming Signal**
Pretend a "sensor register" byte arrives from outside. Decode which
bits are set and report which subsystems it's telling you about.
*(skills: reading/decoding bitfields — this is exactly what real
register reads look like)*

**Mission 3.5 — Wire It Into the Menu**
Add a menu option: "Control subsystems" that lets the operator flip
bits interactively.
*(ties back to Stage 1's menu system)*

---

## Deliverable

A new `systems.c` / `systems.h` module, wired into the outpost menu,
that controls subsystems purely through bitmasking on a single
status byte — no separate boolean variable per subsystem.

This is the closest Stage 3 gets to real hardware without touching
any yet. Stage 5 reuses this exact logic on an actual Arduino.
