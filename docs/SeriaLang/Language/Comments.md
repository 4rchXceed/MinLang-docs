# Comments

Comments in SeriaLang are used to annotate code and provide explanations or notes for developers. They are ignored by the compiler and do not affect the execution of the program.

## Whole Line Comments
Whole line comments start with `//` and continue until the end of the line.

```ucl
// This is a whole line comment
```

## Inline Comments
Inline comments also start with `//` and continue until the end of the line. They can be placed at the end of a line of code.

```ucl
Int myVar = 10 // This is an inline comment
```

## What if you need to print "//"?
You can use a backslash `\` to escape the `//` sequence.
```ucl
print("This is not a comment: \/\/")
```

## Multi-line Comments

Not supported (yet)