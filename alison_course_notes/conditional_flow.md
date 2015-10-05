# Conditional Flow
- How can an electronic device compare two values?
  - Determine if the result of subtracting the two values is zero
  - No matter how you subtract the two values, they are equal if and only if the result is zero
  - This outcome can be remembered with a single bit (on or 1 for equal, off or 0 for anything else)
- In machine code, control flow might look something like an instruction that says (given a certain bit) 'jump if not zero'

### In C
```
  if (condition) {
    run_this_code
  }
```
or nested
```
  if (condition) {
    if (second_condition) {
      run_this_code
    }
  }
```
- use double equals for comparisons `==`
- logical AND `&&` and OR `||` 