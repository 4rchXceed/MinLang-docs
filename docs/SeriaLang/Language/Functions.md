# Functions

There's (like variables) a lot to say about functions.

## Creation

Functions are defined using the `fun` keyword, followed by the function name, parameters (if any), and a colon (`:`). The function body is indented below the function definition.

```ucl
fun MyFunction():
    Print()<"Hello, World!">
MyFunction
```

## Closing a Function
A function is closed by writing its name again on a new line, without any indentation.

```ucl
fun MyFunction():
    Print()<"Hello, World!">
MyFunction
```

## Function Parameters

Function parameters are defined within the parentheses following the function name. Each parameter must have a name and a type.
Parameters are separated by semicolons (`;`).

```ucl
fun Test(Int a; Int b;):
    Print()<"1">
Test
```

Parameters can be of any type, including `Void` (yes).
No default values for parameters.

### Accessing Parameters
A parameter is a local variable, so you can access it using the `#::` prefix:

```ucl
fun Test(Int a; Int b;):
    #::a::Add(1)  // Adds 1 to the parameter 'a'
Test
```

## Return Values

Not yet supported, but will be in the future.

## Calling Functions

To call a function, simply write its name followed by parentheses and angle brackets. If the function has parameters, provide the arguments within the angle brackets, separated by semicolons (`;`).

```ucl
fun Greet(String name):
    Print()<"Hello, " + #::name + "!">
Greet

fun Main():
    Greet()<"Alice">
Main
```

If the function has no parameters, you can call it with empty angle brackets:

```ucl
fun SayHello():
    Print()<"Hello!">
SayHello

fun Main():
    SayHello<>
Main
```

## Main Function
The `Main` function is a special function that serves as the entry point of the program. It is called automatically when the program starts.

```ucl
fun Main():
    Print()<"This is the main function!">
Main
```

You can have only one `Main` function in your program.

## Recursive Functions

Functions cannot call themselves directly (no direct recursion). However, you can achieve recursion by using an intermediary function.

```ucl
fun MainCall():
    Main()<>
MainCall

fun Main():
    MainCall()<>
Main
```

## Function Naming

Function names must start with a letter (a-z, A-Z) or an underscore (`_`), followed by any combination of letters, digits (0-9), or underscores. Function names are case-sensitive.

```ucl
fun myFunction():
    Print()<"This is my function!">
myFunction
```

## Function Flags
Functions can have flags that modify their behavior. Flags are specified before the `fun` keyword.

### ascode

The `ascode` flag indicates that the function should copy it's code, and hardcode every parameters when called.
What does that mean?

When you call a function with the `ascode` flag, the function's code is copied and pasted in a new function (name[nbr_of_functions]), with all parameters replaced by their actual values.
Why?
As you know, Minecraft supports only Int local variables. So if you want to use a function with parameters other than Int (e.g. String), you need to use the `ascode` flag.

Limitation: You cannot change the value of a parameter inside an `ascode` function. (Because it's hardcoded), nor call it with a value type that is not literal or global variable.

```ucl
ascode fun WhileGt(String var; Int value; String callback;):
    If (#::{$::var} > $::value): Execute()<$::callback>
    If (#::{$::var} > $::value): Execute()<$::self>
WhileGt
```

### The self global variable

The self global variable is a function pointer to the current function. It can be used to call the current function recursively (indirect recursion only).

```ucl
ascode fun WhileGt(String var; Int value; String callback;):
    If (#::{$::var} > $::value): Execute()<$::callback>
    If (#::{$::var} > $::value): Execute()<$::self>
WhileGt
```

 $::self is the function pointer to the current function (WhileGt in this case).