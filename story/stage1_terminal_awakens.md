# Stage 1: The Terminal Awakens

## The Story

Deep in your brother's homemade server, you find an old, dusty control
terminal — remnant of some long-abandoned "Outpost" project. You power
it on. It hums, flickers... and prints garbage.

Your job: get it talking properly.

---

## Missions

**Mission 1.1 — First Contact**
Make the terminal print a boot message when it starts.
*(skills: `printf`, compiling with gcc)*

**Mission 1.2 — Identify the Operator**
The terminal should ask for the operator's name and greet them by it.
*(skills: `scanf`/`fgets`, format specifiers, watch out for `%c` vs `%s` gotchas)*

**Mission 1.3 — The Command Menu**
Build a menu:
```
1) Status report
2) Exit
```
Reading operator input decides what happens next.
*(skills: `if`/`else` or `switch`)*

**Mission 1.4 — Keep It Running**
Right now the terminal runs once and dies. Make the menu loop until
the operator chooses to exit.
*(skills: `while` or `do-while` loops)*

**Mission 1.5 — Modularize the Status Report**
Pull the status-report logic out into its own function,
`print_status()`, called from the menu.
*(skills: functions — declaring, defining, calling)*

---

## Deliverable

`outpost.c` — a single-file program that:
- Prints a boot message
- Greets the operator by name
- Shows a looping menu
- Calls a separate function for at least one menu action

This is the seed of everything that follows. Keep this file — Stage 2
builds directly on top of it.
