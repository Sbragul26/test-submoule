### Completed Improvements

- The function assumes the structure of `jsonInput` is always correct. **Added validation** for the presence and types of `nodes` and `edges` before proceeding.
- There are many hardcoded default values (e.g., `"https://default.api.com"`, `"api_response"`, etc.). **Removed these hardcoded values** and replaced them appropriately.
- We currently don't need those variables at the bottom. **Removed unnecessary variables.**
- Just call all the functions (nodes) inside the main function for now (including for Python). **Refactored main function accordingly.**
- Later arguments can be added manually to test the code. **Confirmed structure allows for easy future extension.**
- The file is very large and mixes code generation for multiple languages in a single file. **Separated logic into language-specific files for better maintainability.**

### Output

![Arithmetic Code Generation](https://github.com/Sbragul26/test-submoule/blob/main/arithmetic-cnew.gif)
