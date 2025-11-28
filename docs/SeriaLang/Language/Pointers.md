# Pointers in SeriaLang

Due to the lack of variable types in MinLang, pointers was a requirement

## Function pointer

### Creation

With the syntax `<%[FUNCTION EXPRESSION]%>` you can create a function pointer, this will replace the expression with the compiled (MinLang) code to run the function

Example:
```ucl
IfEntityInRange()<"creeper"; 15; <%PrintMessage()<>%>>
```

### Calling

You can't call a function pointer in vanilla SeriaLang, you need to check the execute function of your runtime, if it supports function pointers.

(Example with MinLang runtime):
```ucl
// Source code of stdlib
%import execute.uchc

ascode fun WhileLt(String var; Int value; String whileLtCallback;):
    If (#::{$::var} < $::value): Execute()<$::whileLtCallback>
    If (#::{$::var} < $::value): Execute()<$::self>
WhileLt
```