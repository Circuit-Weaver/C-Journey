# rawan compiler 

compile c file and run it

c script that take and input c file

then compile that c file and run it

## 1. compile
```bash
gcc program.c -o program
```
## 2. run
```bash
./program
```

## Script CLI

```bash
rcc program.c
```

To make it work as a real command:
```bash
chmod +x rcc # make it executable
sudo mv rcc /usr/local/bin/   # put it somewhere in your PATH
```
Now you can just type rcc program.c from anywhere on your brother's server, and it'll compile and run it in one shot.


## Ideas for your "keep improving it" list, in rough order of difficulty:

1. Show the actual gcc error nicely if compilation fails (right now it just silently doesn't run).
2. Add a -o flag so the compiled binary doesn't clutter the folder (compile to /tmp or a bin/ folder).
3. Pass extra arguments through to the program itself (e.g. rcc program.c hello 5).
4. Add compiler warnings by default (-Wall -Wextra) — this will save you SO much debugging pain once your programs get bigger.
5. Eventually: support multiple .c files at once.

That last one about -Wall -Wextra is genuinely worth adding soon — since you just fought through %c/%s/scanf/fgets issues, the compiler warnings would've flagged a lot of that for you automatically.