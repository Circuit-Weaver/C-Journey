# C Cheat Sheet

## 1. Basic Program Structure

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

---

# 2. Variables and Data Types

```c
int age = 20;
float price = 19.99;
double pi = 3.1415926535;
char grade = 'A';
char name[] = "Alice";
```

| Type     | Size (Typical) | Example   |
| -------- | -------------- | --------- |
| `char`   | 1 byte         | `'A'`     |
| `int`    | 4 bytes        | `42`      |
| `float`  | 4 bytes        | `3.14f`   |
| `double` | 8 bytes        | `3.14159` |
| `long`   | 4 or 8 bytes   | `100000L` |

---

# 3. Input and Output

### Output

```c
printf("Age = %d\n", age);
printf("Price = %.2f\n", price);
```

### Input

```c
scanf("%d", &age);
scanf("%f", &price);
scanf(" %c", &grade);
```

---

# 4. Format Specifiers

| Specifier | Meaning      |
| --------- | ------------ |
| `%d`      | int          |
| `%f`      | float        |
| `%lf`     | double       |
| `%c`      | char         |
| `%s`      | string       |
| `%u`      | unsigned int |
| `%x`      | hexadecimal  |
| `%p`      | pointer      |

---

# 5. Operators

### Arithmetic

```c
+  -  *  /  %
```

### Comparison

```c
== != < > <= >=
```

### Logical

```c
&&
||
!
```

### Assignment

```c
=
+=
-=
*=
/=
%=
```

---

# 6. If Statements

```c
if (age >= 18) {
    printf("Adult");
}
else if (age >= 13) {
    printf("Teen");
}
else {
    printf("Child");
}
```

---

# 7. Switch

```c
switch(choice) {
    case 1:
        printf("One");
        break;

    case 2:
        printf("Two");
        break;

    default:
        printf("Invalid");
}
```

---

# 8. Loops

### for

```c
for (int i = 0; i < 5; i++) {
    printf("%d\n", i);
}
```

### while

```c
while (x < 10) {
    x++;
}
```

### do-while

```c
do {
    x++;
} while (x < 10);
```

---

# 9. Functions

```c
int add(int a, int b) {
    return a + b;
}

int main() {
    int sum = add(5, 3);
}
```

Function prototype:

```c
int add(int, int);
```

---

# 10. Arrays

```c
int numbers[5] = {1,2,3,4,5};

printf("%d", numbers[0]);
```

Loop:

```c
for (int i = 0; i < 5; i++) {
    printf("%d\n", numbers[i]);
}
```

---

# 11. Strings

```c
char name[20] = "Alice";
```

Useful functions (`<string.h>`):

```c
strlen(str);
strcpy(dest, src);
strcat(dest, src);
strcmp(a, b);
```

---

# 12. Pointers

```c
int x = 10;
int *p = &x;

printf("%d", *p);
```

| Symbol | Meaning     |
| ------ | ----------- |
| `&`    | Address of  |
| `*`    | Dereference |

---

# 13. Pointer Example

```c
int x = 5;
int *p = &x;

*p = 20;

printf("%d", x);   // 20
```

---

# 14. Structures

```c
struct Student {
    char name[20];
    int age;
};

struct Student s = {"Alice", 20};

printf("%s", s.name);
```

---

# 15. Enums

```c
enum Day {
    MON,
    TUE,
    WED
};

enum Day today = MON;
```

---

# 16. File I/O

```c
FILE *fp = fopen("file.txt", "r");

if (fp != NULL) {
    fclose(fp);
}
```

Write:

```c
fprintf(fp, "Hello");
```

Read:

```c
fscanf(fp, "%d", &x);
```

---

# 17. Dynamic Memory

```c
#include <stdlib.h>

int *arr = malloc(10 * sizeof(int));

free(arr);
```

Other functions:

```c
calloc()
realloc()
free()
```

---

# 18. Common Header Files

```c
#include <stdio.h>    // printf, scanf
#include <stdlib.h>   // malloc, free
#include <string.h>   // strlen, strcpy
#include <math.h>     // sqrt, pow
#include <ctype.h>    // toupper, isdigit
#include <time.h>     // time
```

---

# 19. Useful Math

```c
sqrt(x);
pow(a, b);
abs(x);
ceil(x);
floor(x);
```

---

# 20. Preprocessor

```c
#define PI 3.14159

#define SQUARE(x) ((x)*(x))
```

Conditional compilation:

```c
#ifdef DEBUG
printf("Debug mode");
#endif
```

---

# 21. Common Escape Sequences

| Escape | Meaning      |
| ------ | ------------ |
| `\n`   | New line     |
| `\t`   | Tab          |
| `\\`   | Backslash    |
| `\"`   | Double quote |
| `\'`   | Single quote |

---

# 22. Command-Line Arguments

```c
int main(int argc, char *argv[]) {

    printf("%d\n", argc);

    return 0;
}
```

---

# 23. Memory Layout (Conceptual)

```
Stack
↑
Local variables
Function calls

Heap
Dynamic memory (malloc)

Data
Global/static variables

Text
Program code
```

---

# 24. Compilation

Using GCC:

```bash
gcc program.c -o program
```

Run:

```bash
./program
```

With warnings:

```bash
gcc -Wall -Wextra program.c -o program
```

---

# 25. Common Pitfalls

* Initialize variables before use.
* Always check the return value of `malloc()` and `fopen()`.
* Match `malloc()` with `free()`.
* Avoid buffer overflows.
* Use `==` for comparison, `=` for assignment.
* Remember array indices start at `0`.
* End every statement with `;`.
* Use braces `{}` for clarity, even with single-line `if` statements.

---

## Quick Reference

```c
// Comment

/* Multi-line
   comment */

int x = 5;
float y = 3.5f;
char c = 'A';

if (...) {}
else {}

switch (...) {}

for (...) {}

while (...) {}

do {} while (...);

int func(int a);

int arr[10];

char str[20];

int *ptr = &x;

struct Person {};

FILE *fp;

malloc();
free();
```

This cheat sheet covers the core syntax and standard library features you'll use most often in C programming, from variables and control flow to pointers, memory management, file handling, and compilation.
kw