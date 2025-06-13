### Code Updates Summary ( Completed)

- **Refactored `useCodeGenerator` Hook**  
  Updated the `useCodeGenerator` hook to use a `switch-case` structure for handling specific language-based code generation logic directly via hardcoded calls. This simplifies debugging for each language block also provided intended required code.

- **Renamed Arithmetic Nodes**  
  Changed the names of arithmetic operation nodes for clarity and consistency (e.g., `Addition`, `Subtraction`, etc.).

- **Added `jsonInput` Validation**  
  The function previously assumed the structure of `jsonInput` was always valid.  
  Now includes validation checks for the **presence and correct types** of `nodes` and `edges` before proceeding.



