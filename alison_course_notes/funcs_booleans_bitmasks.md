# Functions
- You can declare functions at the top of a file (before main function) if it won't be defined at the point in the program that it's called
  - ie `int my_function(void)`
- Functions can be called from other functions as long as they're defined before being called
- Functions should not be defined from inside of another function
- Any given function should have a name, a return type, and arguments
  - No return value of arguments should be declared as `void`

# Booleans
- You can think of a bit as a kind of boolean, since it will either be a 1 or 0

### Boolean Operators
- NOT
  - just flips the input, NOT 1 is 0, NOT 0 is 1
- AND
  - both
- NOR
  - neither one
- NAND
  - not both

# Bitmasks
- Indicate that you're using a binary number by prefixing numbers with 0b
- Bitmasks can be used to determine if a character is uppercase or lowercase