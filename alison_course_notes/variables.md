# Variables
- When declaring a variable, you must indicate the size, and the data type, as well as the name that you want to refer to the data by
- So, for `short unsigned int total = 5;`
  - `0000 0000 0000 0101`
  - `short` still indicates 2 bytes here, so there is quite a bit of unused memory
  - There is no bit used for signing

- A declared variable can store the return value of a function that returns the same data type as the declared variable
  - For `int total = 5;`, total can be reassigned to store the return value of any function that returns an int
  - For `total = total + printf("something");` total would be reassigned to equal 14, because printf returns the number of characters that it printed

- To print a variable `printf("Displaying a number, %d", total)`, the second arg is placed in the %d's place
  - This can be done with an arbitrary number of %d's

### Terminating Strings of Text
- When a function is running through a string, how does it know when it has reached the end and what data actually belongs to the string?
- Usually you use a terminating byte, which is just eight zeros (null character)
  - Function knows to stop when it hits the null character
  - The size of the string of text is whatever you had plus the null character
  - If a string is not properly terminated, every following byte in memory will be interpreted and printed as an ascii character (until a null terminator is reached)
  - This could result in strange text being written in a print function, or strange music being played from a music playing program
- You could prevent this by telling a function to stop printing or reading after a certain number of bytes, or by using a null terminated string

### More on `printf`
- In printf("123"), the "123" will look like: `0011 0001 0011 0010 0011 0011`
- the placeholder in printf must match the data type of the variable being passed in, because the above binary would mean different things depending on whether it was representing an int or the string "123"
- `%d` OR `%i` can be used as placeholders for a `signed int`
- `%u` is used for an unsigned int
- `%c` can be used for a SINGLE character
- `%s` can be used for a null terminated string
  - Any string that you initialize enclosed with double quotes will include a null terminator by default
    - So "123" is 4 bytes (one for each char and one null terminator)
- Important to note that a single char is not null terminated, it is one byte
- Placeholders in `printf` must be matched up in order of the arguments passed in