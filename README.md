# Code Generation and Arithmetic Nodes Features Documentation

This document outlines two features:
1. **JSON to Code Converter** for generating code in multiple languages.
2. **Arithmetic Operation Nodes** with a properties window in a ReactFlow canvas.

Each section includes goals, components/hooks used, and newly added functions, organized by file paths.

---

## Feature 1: JSON to Code Converter

### Goal
Convert JSON data into code for languages like **C**, **C++**, **Python**, and **XML**, with an optional button to **run** the generated code.

---

### Hooks

- **Hook Name**: `actions.jsx`  
  **File Path**: `src/hooks/actions.jsx`

---

### New Functionality

- Converts JSON data (in Node and Edge formats) to C, C++, Python, or XML code.
- Saves the generated code in `public/generated-code` directory for easy and global use.
- Adds an optional button to **run** the generated code.
- Updated `next.config.js` to enable the server side rendering actions and operations.

---

### Functions

#### File: `src/hooks/actions.jsx`

##### `generateCode({ jsonInput })`
- **Description**: Transforms JSON data into code for the intended language.
- **Parameters**:
  - `jsonInput` – Node and Edge data in JSON.
  - Target language (e.g., `"C"`, `"C++"`, `"Python"`, `"Java"`, `"Javascript"`, `"Xml"`).
- **Returns**: `string` – The generated code and saved in public/generated-code directory
- ### Note
-   if the output files already existed , it over-writes the currect file so no duplicate files occured.
-   
---

#### File: `src/hooks/useAction.tsx`

##### `useAction()`
- **Description**: A custom hook to manage JSON-to-code conversion and execution.
- **Returns**: `object` – Includes `convertJsonToCode`, `executeGeneratedCode`.

---

#### File: `next.config.js`

- **Description**: Updated to support JSON handling and code generation capabilities.

- `/** @type {import('next').NextConfig} */
const nextConfig = {
  serverActions: true, // Enables server-side rendering for dynamic code operations
};

module.exports = nextConfig;`

---

#### File: `src/pages/page.tsx`

##### `handleGenerateCode`
- **Description**: A functions to perform the action hook , this function will execute when the `Generate code` button is clicked (a dummy button to trigger code execution).
- **Returns**: `None`.

---

## Feature 2: Arithmetic Operation Nodes with Properties Window

### Goal
Enable arithmetic operation nodes (add, subtract, etc.) in a **ReactFlow** canvas, with a **Properties Window** to configure nodes and modify input/output data types. These configurations are also embedded into the code generation.

---

### 🧠 Hooks

- **Hook Name**: `useFlow`  
  **File Path**: `src/hooks/useFlow.tsx`

---

### 🧩 Components

- `src/components/properties/index.tsx`
- `src/components/Node/Node.tsx`

---

### 🆕 New Functionality

- Add arithmetic operation nodes to canvas.
- Use properties window to:
  - Configure nodes.
  - Modify data types.
- Double-click node to open editor.
- Embed configurations into code generation logic.

---

### 🔧 Functions

#### 📄 File: `src/hooks/useFlow.tsx`

##### `Arithmetic_node`
- **Description**: Adds an arithmetic node to the canvas.
- **Parameters**:
  - `nodeType: string` – Type of arithmetic operation.
  - `position: { x: number, y: number }` – Canvas coordinates.
- **Returns**: `void`

##### `updateOnDoubleClick(nodeId: string)`
- **Description**: Opens properties window for the selected node.
- **Parameters**:
  - `nodeId: string` – ID of the node.
- **Returns**: `void`

---

#### 📄 File: `src/components/PropertiesWindow.tsx`

##### `openPropertiesWindow(nodeId: string)`
- **Description**: Launches the configuration UI for a node.
- **Parameters**:
  - `nodeId: string`
- **Returns**: `void`

##### `updateNodeDefinition(nodeId: string, definition: ArithmeticDefinition)`
- **Description**: Saves arithmetic setup for the node and includes it in code generation.
- **Parameters**:
  - `nodeId: string`
  - `definition: ArithmeticDefinition`
- **Returns**: `void`

---

#### 📄 File: `src/components/Node/Node.tsx`

##### `alterDataType(nodeId: string, inputType: string, outputType: string)`
- **Description**: Modify a node’s data types via properties window.
- **Parameters**:
  - `nodeId: string`
  - `inputType: string`
  - `outputType: string`
- **Returns**: `void`

---

#### 📄 File: `src/pages/page.tsx`

##### `renderPropertiesWindow()`
- **Description**: Displays the properties window for UI interaction.
- **Returns**: `JSX.Element`

---

## ✅ Summary

This documentation highlights the integration of:
- A multi-language code generation engine from JSON.
- A visual arithmetic logic system using ReactFlow.
- A configurable UI for defining node behavior and data types.

---

