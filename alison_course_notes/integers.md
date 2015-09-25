### Signed vs Unsigned Integers
- You can store a 7 using 3 bits, but you would need 4 bits to store 8, and 5 to store 16
- Adding one bit to any binary sequence doubles its capacity
- You could instead use the far left bit as a flag to indicate whether or not the number is positive or negative, but this changes the value of that chunk of data
  - For this reason, it is important to know whether a number is 'signed' or 'unsigned'
  - There is a problem with doing things this way alone because now you can represent zero in two ways (positive or negative)
  - `1010` could mean decimal 10, or decimal -2

### Basics of Numeric Overflow
- Any time you fill up all of the bits you have available with ones, the next number will add an extra column on the left with a one, and all of the previous ones will become zeros
- If your program is expecting that you only have 3 bits, then 7 + 1 will look like `000` because the 1 in `1000` cannot be stored
  - For this reason, adding two valid numbers can result in an incorrect number being produced if it is too large to be stored in the number of bits allocated

### Fractional Numbers in Binary
- Before the decimal you have 8 4 2 1 .
- After you have ½ ¼ ⅛
- So, for 6 and half you would have 0110.1
- But for decimal 6.1, there is no 1/10 place, so you end up estimating by adding more and more digits of 1/16 or 1/32.
- For some decimal numbers, it is possible to give this exact number with enough fractional binary digits
- Since you can't store a decimal point, you have to store the number of bits in the integer portion of the number, and the number of bit that represent the decimal (after the point) portion
- The more bits you have available to you, the more accurately you can store the floating point number

### Numeric Data Types in C
- We need to give numbers a set size, so the CPU knows how much memory to allocate for that number
- The maximum number that can be stored given a certain number of bits will be much smaller if it's going to be a signed number
- Declaring a variable number as `int` means you can have any whole number which can be positive or negative, int defaults to signed int and means the same thing as declaring something as `signed int`
- Declaring that same variable as `unsigned int` means you can only use positive integers
- `float` will support fractional values, and will automatically include a sign bit as well

###### Size Modifiers   
- Each data type has a max number it can hold
- Keyword `long` can be used to allocate more space for the int
- Keyword `short` can be used to allocate less space for the int
- `unsigned short int counter = 5;` means:
  - allocate space for an unsigned (necessarily positive) int with less space and initialize it as a 5
- Max number for unsigned will be 2 to the power of (whatever the number of bits is) minus 1
  - So for a numeric data type stored in 2 bytes (16 bits) the max number you could hold would be (2^16) - 1, or 65,535
- Max number for a signed integer is (2ⁿ/2) - 1, and the minimum number will be 2ⁿ/-2
  - So for 2 bytes, max value would be 32,767 and min number would be -32,768  