# If and For Statements

## If Statement

The `If` statement is used to execute a function based on a condition. The syntax is as follows:

```ucl
If (#::myLocalVar = 1): PrintMsg()<>
```

### Condition

- The condition must be a comparison between a local variable and a literal value.
- The comparison is handled by the compiler, not by the SeriaLang interpreter.
- The condition can only be `=` (equal), `<` (less than), `>` (greater than), `<=` (less than or equal to), `>=` (greater than or equal to).
- Adding ! before the comparison operator will negate the condition (e.g., `!=`, `!<`, `!>`, `!<=`, `!>=`).
- The local variable must be of type `Int`.
- The literal value must be of type `Int`.
- You can compare a local variable to another local variable
- You can compare a local variable to a global variable
- You can compare a global variable to another global variable (the result will be hardcoded)
- You can compare a global variable to a literal value (the result will be hardcoded)

### Function Call

- You can pass parameters to the function being called.

## For Statement

The `For` statement is used to execute a function multiple times based on a condition. The syntax is as follows:

```ucl
For (0; 10; 1) -> i: MyFun()<>
```

About this example:

- The loop will start at `0` and end at `10`, incrementing by `1` each time.
- The loop variable is `i`, which will take the values from `0` to `9`.
- The function `MyFun` will be called `10` times, with `i` taking the values from `0` to `9`.
- You can pass `i` as a parameter to the function being called.
- You can pass the loop variable as a parameter to the function being called.

### Start, End, Step
- The `start`, `end`, and `step` values must be literal values of type `Int`.
- The `start` value is inclusive, meaning the loop will start at this value.
- The `end` value is exclusive, meaning the loop will end before this value.
- The `step` value is the amount by which the loop variable will be incremented/decremented each time.

### Function Call

Same as the `If` statement.

### Additional Notes

The for loop is managed by the compiler, not by the SeriaLang interpreter. This means that the loop will be unrolled at compile time, and the resulting code will be a series of function calls.