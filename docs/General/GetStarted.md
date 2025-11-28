# Get started

## Please start by reading the language's documentation

## Install the compiler

You can download the latest release of the compiler from the [releases page](https://github.com/4rchXceed/MinLang/releases)

## Run the compiler

In each release you'll find these files:
- *.dll, .pdb, .json: .NET assemblies required to run the compiler
- run.sh: Bash script to run the compiler on Linux/MacOS
- run.ps1: PowerShell script to run the compiler on Windows

## Create your first program

Create a file named `hello.ucl` in a folder named `projet1` and add the following code:
```
%import print.uchc

fun Main():
	Print()<"Hello World">
Main
```
Then run the compiler with:
- On Linux/MacOS:
`./run.sh projet1/hello.ucl <coordinates>`
- On Windows:
`.\run.ps1 projet1/hello.ucl <coordinates>`

coordinates: The coordinates where you want the command blocks to be generated (format: x,y,z)

(The Main function is the entry point of the program) -> [Functions](../SeriaLang/Language/Functions.md)

You should see a folder named `bin` with a file named `main` inside, containing the generated Minecraft command(s).

If you see multiple lines, you can copy-paste them all in a command block in Minecraft. (avoid using *chain* command blocks, as this could cause issues with the execution order)

Congratulations, you just created and ran your first SeriaLang program!

## Issues
If you encounter any issues, please report them on the [GitHub issues page](https://github.com/4rchXceed/MinLang/issues)