# C Roadmap (toward Arduino / Embedded EE)

A rough path, not a strict order — you're learning by curiosity, so
jump around as things come up naturally. Use this to know roughly
where you are and what's still ahead.

---

## Stage 1: Foundations (you're here / just past here)

- [x] Variables, types (`int`, `char`, `float`, `double`)
- [x] `printf` / `scanf` / `fgets` and format specifiers (`%d`, `%c`, `%s`)
- [ ] `if` / `else`, `switch`
- [ ] Loops: `for`, `while`, `do-while`
- [ ] Operators: arithmetic, comparison, logical (`&&`, `||`, `!`)
- [ ] Functions: declaring, defining, calling, return values
- [ ] Basic arrays

**Milestone project idea:** a small CLI calculator or a number-guessing game.

---

## Stage 2: Core C (the real meat)

- [ ] Pointers — what they are, pointer arithmetic, pointers to pointers
- [ ] Arrays and pointers (how they relate to each other)
- [ ] Strings as `char` arrays (no built-in string type in C!)
- [ ] Structs
- [ ] `typedef`
- [ ] Dynamic memory: `malloc`, `free`, `calloc`, `realloc`
- [ ] File I/O: `fopen`, `fread`, `fwrite`, `fclose`
- [ ] The `#define` preprocessor and macros
- [ ] Multi-file projects: headers (`.h`) vs source (`.c`), `#include` guards

**Milestone project idea:** improve `rcc` to support flags (e.g. `-o`,
`-Wall` by default), or build a simple linked-list based tool (like a
to-do list stored in memory).

---

## Stage 3: Systems-level C (this is where "embedded" starts)

- [ ] Bitwise operators: `&`, `|`, `^`, `~`, `<<`, `>>`
- [ ] Fixed-width integer types: `uint8_t`, `int16_t`, etc. (`<stdint.h>`)
- [ ] Bit flags / bit masking (how you'll flip individual pins later)
- [ ] `volatile` keyword (matters a lot once you touch real hardware registers)
- [ ] Endianness (byte order) — just conceptually for now
- [ ] Structs with bitfields
- [ ] Basic understanding of how memory is laid out (stack vs heap vs
      static/global)

**Milestone project idea:** write a tiny program that manipulates
individual bits of a number to simulate "turning pins on/off" — good
mental rehearsal before touching a real Arduino register.

---

## Stage 4: Toolchain literacy

- [ ] Makefiles (you've already got a head start here)
- [ ] Compiler flags: `-Wall -Wextra -Werror`, optimization levels (`-O0`, `-O2`)
- [ ] `gdb` — stepping through code, inspecting variables, finding segfaults
- [ ] `valgrind` — catching memory leaks/misuse
- [ ] Cross-compilation basics (compiling for a *different* CPU than
      the one you're on — this is exactly what happens when you build
      for an AVR chip on your PC)

---

## Stage 5: Bridge into embedded / Arduino

- [ ] Arduino's C/C++ core — `setup()` / `loop()`, `digitalWrite`,
      `analogRead`, etc. (should feel familiar once Stage 3 is solid)
- [ ] Datasheets — reading pin diagrams and register maps
- [ ] Direct register manipulation (bypassing Arduino's built-in
      functions and writing to hardware registers directly using the
      bitwise skills from Stage 3)
- [ ] `avr-gcc` / `avrdude` — compiling and flashing manually
- [ ] Timers, interrupts, PWM

**Milestone project idea:** blink an LED two ways — once using
Arduino's `digitalWrite()`, once by manipulating the AVR port
register directly. Comparing the two is a great "aha" moment.

---

## How to use this roadmap

- Don't rush Stage 2 → pointers and memory trip up almost everyone,
  and Stage 3 (bit manipulation) leans on them heavily.
- Every "milestone project idea" is optional — replace with whatever
  your brother assigns, or whatever you get curious about.
- Check things off as you go so you can see progress — this list
  will look intimidating on day one and pretty short a few months in.