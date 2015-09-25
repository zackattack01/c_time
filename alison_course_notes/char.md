# Char
- Characters of text typically store one byte per character
- In ascii, all letters map to a binary value
- Data type `char` has a fixed size of 1 byte (8 binary digits)
- all of the capital letters start with 0010
- all lowercase letters start with 0011
- last 5 bits represent 1-26 or a-z
- notice the flag, last bit of the three bit start can be turned off to make the letter uppercase, or turned on to make it lowercase

### The Numbers on Your Keyboard
- These numbers are encoded as a text value of that number, not the quantity itself
- First four bits are 0011, followed by 0000-1001, or 30-39 representing the text (ascii) values of the numbers 0 through 9
- To convert the character value of a number to the integer value (as a binary quantity) you just turn the two leading ones in the 0011 out front into zeros, giving you 0000 0000 for 0, or 0000 1001 for 9