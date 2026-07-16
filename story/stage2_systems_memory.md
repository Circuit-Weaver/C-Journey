# Stage 2: Systems Memory

## The Story

The terminal responds now — but it has amnesia. Every time it shuts
down, it forgets everything: sensors, readings, logs, all gone. An
outpost that forgets its own sensor data is useless. Time to give it
memory, and grow it beyond a single file.

---

## Missions

**Mission 2.1 — Define a Sensor**
Create a struct `sensor_t` with fields like `id`, `name`, and
`reading`.
*(skills: structs, `typedef`)*

**Mission 2.2 — A Registry of Sensors**
Store multiple sensors in an array. Add a menu option to list them
all.
*(skills: arrays of structs, loops)*

**Mission 2.3 — Give It Real Memory**
Save the sensor registry to a file when the terminal shuts down, and
load it back in when it boots.
*(skills: file I/O — `fopen`, `fread`/`fwrite` or `fprintf`/`fscanf`, `fclose`)*

**Mission 2.4 — Split the Codebase**
The terminal's code is getting big. Split it: sensor logic goes in
`sensors.c` / `sensors.h`, the menu stays in `main.c`.
*(skills: multi-file projects, header files, `#include` guards)*

**Mission 2.5 — Grow Dynamically (stretch goal)**
Instead of a fixed-size sensor array, allocate space as new sensors
are registered.
*(skills: `malloc`, `realloc`, `free`)*

---

## Deliverable

A multi-file `outpost` project that:
- Tracks sensors as structs
- Persists sensor data to a file between runs
- Is split across at least 2 source files + headers

This is the same terminal from Stage 1 — now it remembers things.
