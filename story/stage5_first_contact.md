# Stage 5: First Contact

## The Story

The outpost software is solid — but it's only ever talked to itself.
No real sensors, no real subsystems, just simulations. Time to give it
a body. You're wiring your Stage 3 command deck logic into an actual
Arduino, and controlling a real piece of hardware for the first time.

---

## Missions

**Mission 5.1 — Wire the Hardware**
Connect an LED (with a resistor) to a digital pin on the Arduino.
*(skills: breadboarding basics, reading a simple schematic)*

**Mission 5.2 — Speak Arduino's Dialect**
Get familiar with `setup()`, `loop()`, `pinMode()`, `digitalWrite()` —
Arduino's C/C++ core.
*(skills: Arduino framework basics — should feel familiar, it's C underneath)*

**Mission 5.3 — Port the Command Deck**
Reimplement your Stage 3 bit-flag on/off/toggle logic, but instead of
printing status, actually call `digitalWrite()` to control the LED.
*(skills: bridging your bitwise logic to real digitalWrite calls)*

**Mission 5.4 — Go Straight to the Register (the real milestone)**
Bypass `digitalWrite()` entirely. Find the AVR port register for your
pin in the datasheet, and flip the LED using direct register
manipulation with the same bitwise operators from Stage 3.
*(skills: datasheets, `volatile`, direct register access, `avr-gcc`)*

**Mission 5.5 — Compare the Two**
Blink the LED both ways — once through `digitalWrite()`, once through
raw register manipulation — and understand *why* they do the same
thing at different levels of abstraction.

---

## Deliverable

A real, physically blinking LED, controlled by logic that traces
directly back to the bit-flag system you built in Stage 3 — proof
that the "toy" terminal logic you wrote months ago is the exact same
logic that runs real hardware.

This is the finish line of the roadmap — and also just the
beginning of actual embedded work.
