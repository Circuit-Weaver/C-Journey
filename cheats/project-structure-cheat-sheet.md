# C Project Structure Guide

## Why bother with structure?

Right now your projects are probably one `.c` file. That's fine — but the
moment you have more than one file, or want to reuse code between
projects (like `rcc`), a messy folder becomes a real problem. Good
structure = you (and your brother) can find things fast, and `git`
diffs stay clean.

---

## Level 1: Small project (single tool, like `rcc`)

```
rcc/
├── src/
│   └── main.c
├── bin/            # compiled binary goes here (gitignored)
├── .gitignore
├── README.md
└── Makefile
```

**What goes where:**
- `src/` — all your `.c` source files
- `bin/` — the compiled, runnable output. Never commit this to git —
  it's generated from your source, not something you write by hand.
- `README.md` — what the project does, how to build/run it
- `Makefile` — so you don't retype `gcc file.c -o file` forever
- `.gitignore` — tells git to ignore `bin/`, `obj/`, and other junk

---

## Level 2: Growing project (multiple source files)

```
myproject/
├── src/
│   ├── main.c
│   ├── parser.c
│   └── utils.c
├── include/
│   ├── parser.h
│   └── utils.h
├── obj/            # compiled .o files (gitignored)
├── bin/            # final binary (gitignored)
├── tests/
│   └── test_parser.c
├── .gitignore
├── README.md
└── Makefile
```

**New additions explained:**
- `include/` — header files (`.h`). Function declarations and struct
  definitions live here; the actual code stays in `src/`.
- `obj/` — intermediate compiled object files (`.o`), one per source
  file, before they get linked into the final binary. Keeps clutter
  out of `src/`.
- `tests/` — small programs or scripts that check your code actually
  works, kept separate from the "real" program.

---

## Sample Makefile (matches Level 2 structure)

```makefile
CC = gcc
CFLAGS = -Wall -Wextra -Iinclude
SRC = $(wildcard src/*.c)
OBJ = $(patsubst src/%.c, obj/%.o, $(SRC))
BIN = bin/myprogram

all: $(BIN)

$(BIN): $(OBJ)
	@mkdir -p bin
	$(CC) $(OBJ) -o $(BIN)

obj/%.o: src/%.c
	@mkdir -p obj
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -rf obj bin

.PHONY: all clean
```

Run it with just `make`, clean up with `make clean`.

---

## Sample `.gitignore`

```
bin/
obj/
*.o
*.out
```

---

## Naming conventions (common C style)

| Thing | Style | Example |
|---|---|---|
| Variables/functions | `snake_case` | `read_input()`, `line_count` |
| Constants / macros | `UPPER_SNAKE_CASE` | `#define MAX_SIZE 100` |
| Struct names | `snake_case` + `_t` suffix (common convention) | `point_t` |
| Files | `snake_case.c` / `.h` | `file_utils.c` |

---

## Quick rule of thumb

- 1 file → don't overthink it, `src/` + `Makefile` is enough
- Multiple files that depend on each other → split `include/` from `src/`
- Reusable logic across projects → that's when people start making
  their own libraries (a future topic!)