# MinLang + SeriaLang Documentation

## Commands:

- `serialang <source_file> <output_file> [<options>]` - Serialize the .ucl file to a .ucobject file.
- `minlang <source_file> [<options>]` - Compile the .ucobject file into a single Minecraft command (or multiple if it exceeds the command length limit).

## Get started
[Get Started](General/GetStarted.md)

## SeriaLang Documentation Structure:
- [Language](SeriaLang/Language/Overview.md)
    - [Overview](SeriaLang/Language/Overview.md)
    - [Types](SeriaLang/Language/Types.md)
    - [Variables](SeriaLang/Language/Variables.md)
    - [Comments](SeriaLang/Language/Comments.md)
    - [Functions](SeriaLang/Language/Functions.md)
    - [SeriaLang Header File](SeriaLang/Language/ULHC.md)
    - [If And For Statements](SeriaLang/Language/IfAndFor.md)
    - [Importing](SeriaLang/Language/Import.md)
- [Compiler (Advanced)](SeriaLang/Compiler/Exceptions.md)
    - [Exceptions](SeriaLang/Compiler/Exceptions.md)
    - [CommandLine Arguments](SeriaLang/Compiler/CommandLineArguments.md)

## MinLang Documentation Structure:
- [Overview](MinLang/Overview.md)
- [Limitations](MinLang/Limitations.md)
- [Libraries](MinLang/Libraries/stdlib.md)
    - [stdlib](MinLang/Libraries/stdlib.md)
    - [mclib](MinLang/Libraries/libmc.md)
- [Compiler (Advanced)](MinLang/Compiler/Exceptions.md)
    - [Exceptions](MinLang/Compiler/Exceptions.md)
    - [CommandLine Arguments](MinLang/Compiler/CommandLineArguments.md)
