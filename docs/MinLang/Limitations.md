# MinLang Limitations

MinLang operates within the constraints of Minecraft's command system, which imposes several limitations on the features and functionalities that can be implemented. Below are some of the key limitations to be aware of when using MinLang:
1. **Command Length**: Minecraft commands have a maximum length limit (typically 32,767 characters). Complex SeriaLang constructs may generate commands that exceed this limit, requiring splitting or optimization.
2. **Performance Constraints**: The execution speed of Minecraft commands can be slower compared to native code execution. Highly complex logic may lead to performance bottlenecks within the game.
3. **Limited Data Types**: Minecraft commands variables (scorboards) can only handle integer values. This restricts the types of data that can be manipulated directly. (Use ascode workaround for floats and strings)
4. **EVERYTHING IS ASYNC**: Minecraft command execution is inherently asynchronous, which can lead to timing issues when trying to implement synchronous logic from SeriaLang.
5. **Globals Only**: MinLang currently only supports global variables due to the limitations in Minecraft's command structure. Local variable scopes are not supported.