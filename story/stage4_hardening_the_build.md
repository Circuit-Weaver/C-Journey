# Stage 4: Hardening the Build

## The Story

The outpost software is getting complex enough that a silent bug could
be catastrophic — a crash mid-mission, a memory leak that slowly kills
the system over hours. Real engineers don't just hope their code
works. Time to professionalize how you build, test, and debug it.

---

## Missions

**Mission 4.1 — One Command to Build It All**
Write a Makefile for the whole outpost project (`main.c`, `sensors.c`,
`systems.c`, and their headers) so `make` builds everything in one
shot.
*(skills: Makefiles — you've got a head start from the earlier cheat sheet)*

**Mission 4.2 — Zero Warnings Policy**
Recompile with `-Wall -Wextra -Werror` and fix every single warning
until it builds clean.
*(skills: compiler flags, reading and understanding warnings)*

**Mission 4.3 — Break It On Purpose**
Introduce a deliberate bug — a null pointer dereference, an
off-by-one array access, an uninitialized variable. Then find and fix
it using a debugger instead of guesswork.
*(skills: `gdb` — breakpoints, stepping, inspecting variables)*

**Mission 4.4 — Hunt the Leaks**
Run the project through `valgrind` and fix any memory leaks it finds
— especially around your Stage 2 dynamic memory work.
*(skills: `valgrind`, understanding malloc/free pairing)*

---

## Deliverable

The full outpost project:
- Builds with a single `make` command
- Compiles with zero warnings under `-Wall -Wextra -Werror`
- Has had at least one bug found and fixed using `gdb`
- Passes `valgrind` clean, or you've fixed what it flagged

This is the point where "it works on my machine" becomes "I actually
know why it works."
