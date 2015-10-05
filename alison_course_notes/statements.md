# GOTO Statement
- In some cases the instruction pointer should be set to point back to an earlier (or later) point in the program
- This can be done using `goto variable_name_for_position`
  - In assembly language this is known as a 'jump'
  - This is typically managed for you behind the scenes by whatever program you're using
- In a control flow statement, the curly braces are basically labels for the `goto` variables
- Based on the evaluation of the condition in the if statement, the instruction pointer is set to jump to one of two goto variables
  - In python, you might represent these start and end variables with indentation rather than curly braces
  - In Ruby, you would use `do` `end` blocks

# While Loop In C
```
int main(void){
  int height = 5;
  while(height < 10){
    printf("LoopLoop\n");
    height = height + 1;
  }

  return 0;
}
```
- Typical behavior while the program is running is to enter the block of code, we only jump over this block if the condition is not met
  - So a while loop is translated into a 'goto the closing curly brace when the opposite of the given condition is true' statement