# MinLang + SeriaLang Documentation

## Commands:

- `serialang <source_file> <output_file> [<options>]` - Serialize the .ucl file to a .ucobject file.
- `minlang <source_file> [<options>]` - Compile the .ucobject file into a single Minecraft command (or multiple if it exceeds the command length limit).

## SeriaLang Documentation Structure:
- [Compiler](SeriaLang/Compiler/Exceptions.md)
    - [Exceptions](SeriaLang/Compiler/Exceptions.md)
    - [CommandLine Arguments](SeriaLang/Compiler/CommandLineArguments.md)
- [Language](SeriaLang/Language/Overview.md)
    - [Overview](SeriaLang/Language/Overview.md)
    - [Types](SeriaLang/Language/Types.md)
    - [Variables](SeriaLang/Language/Variables.md)
    - [Comments](SeriaLang/Language/Comments.md)
    - [Functions](SeriaLang/Language/Functions.md)
    - [SeriaLang Header File](SeriaLang/Language/ULHC.md)
    - [If And For Statements](SeriaLang/Language/IfAndFor.md)
    - [Importing](SeriaLang/Language/Import.md)