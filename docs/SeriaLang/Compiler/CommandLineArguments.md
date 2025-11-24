# Command Line Arguments

## Usage
program sourceFile.ucl output[.ucobject] [options]

## Options
-c+=verbose: Enables verbose output during the type checking process. (a hella lot of debug prints) (Use it with -c+=no-progress to avoid errors)

-c+=silent: Disables all output except for errors.

-c+=no-progress: Disables progress bar display.

-c+=no-output: Disables output file generation. (Useful for just checking syntax without generating output)

-c+=bypass-warnings: Ignores all warnings during the type checking process. (not recommended)

-c+=bypass-errors: Ignores all errors during the type checking process. (not recommended at all)

-c+=noerror-ignore-bypass: Disables output for ignored errors OR warnings when -c+=bypass-errors / -c+=bypass-warnings is used.

-c+=ignore-<error_code>: Ignores specific error codes during the type checking process. Replace <error_code> with the actual code to ignore. (Check [Exceptions.md](Exceptions.md) for error codes)

-c+=error-printstack: Prints the current stack trace when an error occurs. (Useful for debugging/development purposes)

### Including Paths
-I&lt;path&gt;: Adds a directory to the list of paths to search for imported files.
Multiple -I options can be used to add multiple directories.

-I MUST be in uppercase.

### config.lib.env

In this file, you can set a keyword=path:

```env
STDLIB=path/to/stdlib
```

And then use it in the command line:
`-Istdlib` (or `-ISTDLIB`), but the first one is recommended for readability.

config.lib.env is located in the same directory as the current pwd (where you run the command).