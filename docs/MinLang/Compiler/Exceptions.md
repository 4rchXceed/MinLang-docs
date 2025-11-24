# MinLang Exceptions


1, File not found.

  - The specified .ucobject file could not be located. Please check the file path and try again.

2, Syntax error.

  - There was a syntax error in the .ucobject file. Please check the file for any mistakes.

3, Semantic error.

    - There was a semantic error in the .ucobject file. Please ensure that all constructs are used correctly. [SHOULD NOT HAPPEN]

4, All variables/Function arg must be of type Int (Minecraft scoreboard's only variable is dummy = int)

    - Minecraft only supports integer variables through its scoreboard system. Ensure that all LOCAL variables and function arguments (for non-ascode functions) are of type Int.

5, Function not found.

    - The specified function could not be found. Please ensure that the function name is correct and that it has been defined.

6, Function already exists.

    - A function with the specified name already exists. Please choose a different name for the new function.

7, Variable not initialized [NOT SUPPOSED TO HAPPEN]

    - The variable being accessed has not been initialized. Please ensure that all variables are properly initialized before use.

8, If only supports: [GlobalVar/LocalVar] <|<=|=|>=|> [GlobalVar/Int]

    - The If statement only supports comparisons between Global or Local Variables and either another Global Variable or an Integer using the operators <, <=, =, >=, >.

9, Only Int variables are allowed.

    - Only Integer type variables are supported. Please ensure that all LOCAL variables are of type Int.

10, Generic UCObject error

    - An unspecified error occurred while processing the .ucobject file. Please check the file for any issues.

11, Variable already exists.

    - A variable with the specified name already exists. Please choose a different name for the new variable.

12, Variable doesn't exist.

    - The specified variable could not be found. Please ensure that the variable name is correct and that it has been defined.

13, Only 'Add', 'Sub' and 'Set' operations are allowed on variables.

    - Only the 'Add', 'Sub', and 'Set' operations are supported for variable manipulation. Please use one of these operations.

14, NotImplementedError

    - This feature is not yet implemented. Please refer to the documentation for supported features.

15, I really don't know how you managed to get this error.

    - An unexpected error occurred. Good luck figuring this one out!

16, You can't assign a variable to another variable.

    - Direct assignment between variables is not supported. Please use the 'Set' operation with an integer value instead.

17, Main function not found (it's the entry point of the program).

    - The Main function, which serves as the entry point of the program, could not be found. Please ensure that it is defined correctly. (Should be deleted in future versions)

18, Not enough arguments provided to function.

    - The function was called with fewer arguments than required. Please ensure that all necessary arguments are provided.

19, You can't pass a variable as an argument to a custom define.

    - When calling a custom defined function, you must pass literal values as arguments. Passing LOCAL variables is not supported.

20, Function argument type mismatch.

    - The type of the argument provided to the function does not match the expected type. Please ensure that the correct types are used.


LOCAL = Dynamic vars (INT-only)