# RAM Basics
- Document is loaded into RAM memory so you can edit and work with it
- When you save this, it rewrites what you've done to disc
- When you run a program, it is loaded into memory in the same way 
- Your computer sees the program being run as data just like everything else
- Program is fundamentally a set of ones and zeros representing instructions
- Each instruction is a set of high and low voltage sequences which are transmitted to your CPU chip
- Your CPU chip behaves according to these voltages, following whatever instructions are given (executing the instruction)
- All instructions are followed one after the other (this is program flow)
- There is one final instruction to return control back after program has been fully executed

## Program Flow
- CPU keeps track of the address in memory where the instruction to be executed is held
- After each instruction is completed, the *instruction pointer* is updated
- When the instruction pointer is moved, the completed instruction is not erased, so you can go back and point to this same instruction again
- Functions are given their own places in memory to be pointed to throughout the program

## Some Rules for C

###### Including Files
- Printing functionality comes packaged with c in the standard input/output library
- You can include this with `#include <stdio.h>`
- By including something you're basically giving your program access to the functions and variables declared in your included file

###### Function declarations
- `return_type function_name(arguments) {}`
- `void` as the argument would mean that there will be no arguments passed in, void before the function name would mean no return value
- Must be a `main` function to be run in any given file
  - ie. `int main(void) { }`
- Explicit returns

###### Calling a Function
- `function_name(arguments);`
  - ie. `printf("hello world");`