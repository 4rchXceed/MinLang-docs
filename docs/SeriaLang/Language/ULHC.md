# Universal Language Header File (ULHC)

This file describes the Universal Language Header Code (ULHC) used in SeriaLang. The ULHC is handled by the compiler, and not by the SeriaLang interpreter.

## File Extension
The ULHC files have the `.uchc` extension.

## Purpose

The ULHC does not contain any SeriaLang code. It is used to define "special" functions:
The function (commonly named Custom Define) will have parameters, and a string containing commands to execute. The parameters will be replaced in the command string.

This is useful for defining functions that would be tedious to write in SeriaLang, or that require specific commands that are not easily represented in SeriaLang.

## Syntax

The syntax for defining a ULHC function is as follows:

```ucl
[Print(String message;)] => <say ?message?>
```
- The function name is `Print`.
- It takes a single parameter of type `String` named `message`.
- The command string is `<say ?message?>`, where `?message?` will be replaced by the value passed to the `message` parameter.

## Limitations

The Custom Define functions have some limitations:

- They are not dynamic. You cannot create or modify them at runtime.
- They cannot contain SeriaLang code. Only the command string is allowed.
- They cannot return values. They are purely for executing commands.
- They cannot have local variables or control flow. The command string is executed as-is.

## Example
Here is an example of a ULHC file defining a simple print function:

```uclhc
[Print(String message;)] => <say ?message?>
```

```ucl
fun Main():
    Print("Hello, World!")
Main
```

This will execute the command `say Hello, World!` when the `Main` function is called.

## Why another file format?

Why not?