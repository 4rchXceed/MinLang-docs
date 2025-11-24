# Variables

Halalala variables...
I could do a whole documentation about variables, but I won't.

Value Types:

When I say "Value type" I does not mean the type of the variable. When you need to pass a value to: a variable, a function parameter, etc. the compiler will instanciate a class "Value" that will check the declaration syntax. The value type is the type of the value you are passing. For example, if you have a variable of type `Int` and you want to assign it a value, the value type must be `Int` too. If you try to assign a `String` to an `Int` variable, the compiler will throw an error. BUT: the value can also be a local variable, a global variable, a function call, etc. The compiler will check the type of the value at compile time.

Here's the list of value types:

- GlobalVar Global Variable
- LocalVar Local Variable
- LocalVar (GlobalVar) Local Variable BUT where the name is a global variable
- CodeBlock A string that will hold the instructions/commands to run a function
- Literal A literal (Int, Float, String, Bool, Void)

## Global Variables

Global variables are defined outside of any function or block. They can be accessed from anywhere in the code.

### Creation

```ucl
const String $printText = "Test"
const Void $null = null
```

Their value needs to be defined at the moment of declaration, and they cannot be changed later (because they are `const`).
They can be of any type, including `Void` (yes).
Their value type can be a literal, another global variable, or a "code block" (function call code).

### Access

To access a global variable, just use its name with a `$::` prefix:

```ucl
print($::printText)
```

## Local Variables

Local variables are defined inside a function or block. They can only be accessed from within the function or block they are defined in.

> [!WARNING]
> SeriaLang's variables does not have scope. If you declare a variable named `score`, you will be able to access it everywhere in the code. (This is not a bug, Minecraft's score system is just... bad)
> !!! The ONLY type of a local variable is INT (because Minecraft's score system only supports integers aka dummy)
> You cannot (yet) pass a local variable as a parameter to a function. (I will implement this)

### Creation

```ucl
Int myLocalVar = 1
```

Their value needs to be defined at the moment of declaration, and they can be changed later.

### Access
To access a global variable, just use its name with a `#::` prefix:

```ucl
Print(#::myLocalVar)
```

### Modifying
To modify a local variable, just use its name with a `#::` prefix and then `::Set`, `::Add`, `::Sub`:

```ucl
#::myLocalVar::Set(5)  // Sets the variable to 5
#::myLocalVar::Add(3)  // Adds 3 to the variable (now it's 8)
#::myLocalVar::Sub(2)  // Subtracts 2 from the variable (now it's 6)
```

I'm planning to implement more operations like `Mul`, `Div`, etc.

## Variable Naming
Variable names must start with a letter (a-z, A-Z) or an underscore (_), followed by letters, digits (0-9), or underscores. They are case-sensitive.
Because we use prefixes, as long as a variable name is valid and unique you can use it (even a variable named true is allowed).

## Function call as value (Function pointers)

You can pass a function call as a value to a parameter or a variable. It will return a String containing the commands to execute the function.
Syntax: <%FunctionName()&lt;params...&gt;%>

```ucl
%import libmc/cmd.uchc

ascode fun WhileGt(String var; Int value; String callback;):
    If (#::{$::var} > $::value): Execute()<$::callback>
    If (#::{$::var} > $::value): Execute()<$::self>
WhileGt
```

You can then use the function call as a value:

```ucl
fun Main():
    WhileGt("myLocalVar"; 10; <%Print()<"myLocalVar is greater than 10!">%)<>
Main
```
