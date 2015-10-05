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
- A variable with the data type `pointer` can be used to store a memory address

###### Creating a Pointer
- To create a pointer, put an asterix * in front of the variable name
  - The position of the asterix (the spacing between it and the data type or var name) is not important
  - `int * my_pointer;` creates a variable that contains a memory address, what is located at that memory address needs to be an integer
  - `int my_pointer;` creates an int with the variable name `my_pointer`
  - Basically, you just give it a data type, a *, and a name

###### Assigning a Value to the Pointer
- Variable to be pointed to must already be initialized
- Set the pointer to be equal to the memory address of (`&`) the target variable
- This will look like `my_pointer = &already_declared_variable_with_a_matching_data_type`
  - Or `int *my_pointer = &target_var;`

###### Obtain the Value Stored at that Address
- The pointer itself will always be equal to a memory address
  - I repeat, `my_pointer` will be an address in memory
- Star pointer (`*my_pointer`) will be equal to the value stored in that memory address

###### Just Remember
- `*` is used:
  - To create a pointer
  - To specify "what is at the address of" a pointer (not the memory address itself)

- `&` is used:
  - To specify "the address of" a variable, (not the value of the variable itself) 

###### To Print a Memory Address
- Use `%p` in a `printf`, and pass in the name of the pointer (no *)

###### Using Pointers to Directly Access Memory
- Just like you would reassign a variable, but make sure you reference the value, not the address (`*ptr = 'a';`)
- When you increment a pointer, if it's a pointer to a variable with 2 bytes, C will know that this means to increment the pointer 2 bytes
