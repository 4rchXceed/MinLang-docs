# Overview

SeriaLang is a programming language aimed to be compiled into Minecraft commands. It is designed to have maximum functionality while being under the restrictions of Minecraft commands.

There's no classes. (No OOP at all)

SeriaLang can also be used by other projects.

## What does SeriaLang do?

SeriaLang "compiles" (more like a serializer) a `.ucl` file into a `.ucobject` file. The `.ucobject` file is a JSON file that contains all the data needed to represent the program in a way that is easy for a program to read and execute.

## File Extensions

- `.ucl` - SeriaLang source file.
- `.uchc` - SeriaLang "header" file (we'll see later what this is).
- `.ucobject` - Serialized SeriaLang object file.

## Compiler
The SeriaLang compiler is a command line tool that takes a `.ucl` file and compiles it into a `.ucobject` file. The compiler is written in Python and can be run on any platform that has .NET installed.

## Common Command Line Arguments

(See [CommandLineArguments.md](Compiler/CommandLineArguments.md) for more details)

- -c+=verbose: Enables verbose output during the type checking process. (a hella lot of debug prints) (Use it with -c+=no-progress to avoid errors)

- -c+=no-output: Disables output file generation. (Useful for just checking syntax without generating output)

- -c+=no-progress: Disables progress bar display. (Can be annoying sometimes)

## Exceptions

SeriaLang has a set of exceptions that can be thrown during the compilation process. These exceptions are used to indicate errors in the source code or issues during the compilation process.

(See [Exceptions.md](Compiler/Exceptions.md) for more details)

An exception can be ignored by using the `-c+=ignore-<error_code>` command line argument. Replace `<error_code>` with the actual code to ignore.

It has the following format:

```
[ERROR] SyntaxError: Unknown expression (Code 25)
 --> this syntax does not exists 
 in function <global>: test.ucl:0
```

Where:

1. `SyntaxError: Unknown expression` is the error message.
2. (Code 25) is the error code.
3. `--> this syntax does not exists` is the line of code that caused the error.
4. `in function <global>: test.ucl:0` is the location of the error.

## Literal Types List

- Int
- Float
- String
- Bool
- Void (100% useless)