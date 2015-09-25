# Arrays and Pointers

### Overview of Arrays
- The ascii string of text "abc123" would be represented as:
  - `0110 0001 0110 0010 0110 0011 0011 0001 0011 0010 0011 0011 0000 0000` ← null terminator
- A string of text is a simple form of an array, a collection of single byte chars
- A variable name can be used in two ways, to access the value it represents, and to refer to the address in memory where the value is stored
  - Every memory address in RAM corresponds to a single byte
  - The only thing that is changed when a variable is initialized is the value in the corresponding memory address
  - The programming language should just be creating a connection between the variable name being referenced in your program and the address in memory that it has been given
  - Basically, the variable name is just a pointer, think RAM[variable_name]
- When storing the string "abc123", each char can only fit in one byte of memory in the RAM
  - Important that every single character in the string has it's own address in memory
  - Important that these chars are stored in a contiguous block of memory
- So, if a pointer points to the first address in a block of memory allocated to a string, a function needing access to this variable could run through all of the contigous memory in RAM, reading or printing the character at each address, until it reaches a null character
- There is no relationship whatsoever between a memory address itself and the type of data stored at that address

### Pointers
- a variable with the data type `pointer` can be used to store a memory address
