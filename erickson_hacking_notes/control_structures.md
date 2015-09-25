# Control Structures

### Quick Hierarchy of Programming
```                     
              assembly language
          (first thing after just numbers,
        you would still need to know processor 
        specific details of the architecture)
                      ↓
                  assembler 
  (translates assembly language into machine readable code)
                      ↓
             machine language   OR a compiler can be used to turn a high level language into machine language, 
                                   this is more intuitive and the compiler can take care of processor details
```


### If-then-else and while in C
- Javascript style for the most part, if (cond) {} else {}
- Curly braces not required if there is only one instruction

### Booleans
- No native representation of boolean vars, things are either 1 or 0, any statement of zero is falsey and everything else is truthy

### Functions
- By default, functions can return a value to the caller
- They are labeled by the type of data that will return, ex.

```
int squared(int x)
{
  return x ** 2;
}
```

- Compiler must know about the functions before they are called
  - this can be done by defining the functions above the point that they're called
  - or by using a **function prototype**. A function prototype must tell the compiler:
    - A function's name
    - the return data type
    - the data type of any functional arguments
    - eg. `int factorial(int);`
- A function that has no value to return should be declared as `void`

### Running Source Files
- the file for the source code is only the beginning, it must be compiled into machine language for the architecture in question
- GNU Compiler Collection is a popular one (GCC)
- so if you have your .c file and include relevant header files:
  - these are files that are probably in usr/include/...
  - here we use `#include <stdio.h>` to get the basic I/O functionality needed for printf, puts etc
- in the command line `gcc FILENAME.c` and this should produce a compiled file
  - default name is a.out
- in the command line `./a.out` will run the compiled source code

### So you've got an executable binary huh
- the cool kids want more
- gnu dev tools has an `objdump` program that lets you look at the compiled binaries
- `objdump -D a.out | grep -A 20 main.;`
  - pipes the output of objdump to grep with the option to only display 20 lines after matching the regexp main

#### First some notes on computer memory
- Each byte is represented in hex, since each byte has 256 possible values, it can be represented with 2 hex digits
- The hex outputs from objdump are each memory addresses
- There are 32-bit (older processor) and 64-bit memory addressing schemes