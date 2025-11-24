# Importing

In SeriaLang, you can import other files using the `%import <fname>` keyword followed by the file path in quotes. This allows you to reuse code across multiple files and organize your project more effectively.

## Syntax

```ucl
%import path/to/your/file.seria
```

You can import multiple files by using multiple `%import` statements.
You can also import files with different extensions, such as `.uchc` for Universal Language Header Code files.

The functions/global variables named in the imported files will be available in the current file, so you cannot have two functions/global variables with the same name in different files.


## File Paths
The file path can be relative, absolute or included in the command line arguments (see [CommandLineArguments.md](../Compiler/CommandLineArguments.md)).:
- **Relative Path**: The path is relative to the current file's location. For example, if your current file is located in `src/` and you want to import a file located in `src/lib/`, you would use `%import lib/file.ucl`.
- **Absolute Path**: The full path to the file from the root of the filesystem. For example, `%import /home/user/project/src/lib/file.seria`.
- **Included Paths**: You can specify additional directories to search for imported files using the `-I<path>` command line argument when running the SeriaLang compiler. For example, if you have a directory `src/includes/` that contains files you want to import, you can run the compiler with `-Isrc/includes/` and then use `%import file.ucl` in your code.
> [!WARNING]
> If two files with the same name are found in different included paths, I don't know what will happen (end of the world?).

## Example

`main.ucl`:
```ucl
%import libmc/print.uchc

fun Main():
    Print("Hello, World!")
Main
```

`libmc/print.uchc`:
```uclhc
[Print(String message;)] => <say ?message?>
```