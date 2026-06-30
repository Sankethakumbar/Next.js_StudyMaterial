The natural next file after **11_React_Components_Fundamentals.md** should be:

# Functional Components

## Topics Covered

1. What is a Functional Component?
2. Rules of a Functional Component
3. Component Syntax
4. Returning JSX
5. Single Root Element Rule
6. Exporting Components (`export default`)
7. Importing Components (`import`)
8. Using Components as Custom Tags
9. Complete Component Flow
10. Quick Recap
11. Interview Questions

---

# What is a Functional Component?

A **Functional Component** is a JavaScript function that returns JSX. It tells React what UI should appear on the screen.

```jsx
function Welcome() {
  return <h1>Hello React!</h1>;
}
```

> Modern React mainly uses **Functional Components** because they are simple and work with Hooks.

---

# Rules of a Functional Component

A Functional Component should:

* ✅ Be a JavaScript function.
* ✅ Start with a **capital letter**.
* ✅ Return valid JSX.
* ✅ Usually return one root element.

Example:

```jsx
function Welcome() {
  return <h1>Hello!</h1>;
}
```

---

# Component Syntax

Basic syntax of a functional component:

```jsx
function ComponentName() {
  return (
    <h1>Hello React!</h1>
  );
}
```

A component consists of:

1. `function` keyword.
2. Component name (Capitalized).
3. `return` statement.
4. JSX to display UI.

---

# Returning JSX

A component must return JSX because JSX describes what should be displayed on the screen.

```jsx
function Welcome() {
  return (
    <div>
      <h1>Hello</h1>
      <p>Welcome to React!</p>
    </div>
  );
}
```

React reads this JSX and renders the UI.

---

# Single Root Element Rule

A component must return **one parent (root) element**.

❌ Incorrect:

```jsx
return (
  <h1>Hello</h1>
  <p>Welcome</p>
);
```

✅ Correct (using `<div>`):

```jsx
return (
  <div>
    <h1>Hello</h1>
    <p>Welcome</p>
  </div>
);
```

✅ Correct (using Fragment):

```jsx
return (
  <>
    <h1>Hello</h1>
    <p>Welcome</p>
  </>
);
```

---

# Exporting Components (`export default`)

To use a component in another file, it must be exported.

```jsx
export default function Welcome() {
  return <h1>Hello React!</h1>;
}
```

`export default` makes the component available outside its file.

> **Simple Analogy:** `export` = sending the component out of the file.

---

# Importing Components (`import`)

To use an exported component, import it into another file.

```jsx
import Welcome from "../components/Welcome";
```

`import` brings the component into the current file.

> **Simple Analogy:** `import` = bringing a tool from another box.

---

# Using Components as Custom Tags

Once imported, a component is used like a custom HTML tag.

```jsx
import Welcome from "../components/Welcome";

export default function Page() {
  return (
    <div>
      <Welcome />
    </div>
  );
}
```

React sees `<Welcome />`, executes the `Welcome()` function, and displays its JSX.

> We use `<Welcome />`, not `Welcome()`, because React can then manage rendering, props, and lifecycle.

---

# Complete Component Flow

```text
Create Component
       ↓
export default
       ↓
Import Component
       ↓
Use <Component />
       ↓
React Executes Function
       ↓
JSX Returned
       ↓
UI Displayed
```

---

# Mini Example

### `components/Welcome.js`

```jsx
export default function Welcome() {
  return <h2>Hello from Welcome Component!</h2>;
}
```

### `app/page.js`

```jsx
import Welcome from "../components/Welcome";

export default function Home() {
  return (
    <div>
      <Welcome />
    </div>
  );
}
```

**Output:**

```text
Hello from Welcome Component!
```

---

# Quick Recap

* Functional Components are JavaScript functions.
* They return JSX.
* Component names must start with a capital letter.
* A component should return one root element.
* Use `export default` to make a component available outside its file.
* Use `import` to bring a component into another file.
* Use components as custom tags: `<Component />`.

---

# Interview Questions

### 1. What is a Functional Component?

A JavaScript function that returns JSX and describes a part of the UI.

### 2. Why are Functional Components preferred?

They are simple, readable, and work naturally with React Hooks.

### 3. What are the rules for naming a component?

The component name must start with a capital letter.

### 4. Why must a component return one root element?

Because JSX must return a single parent element, which helps React build the component tree.

### 5. What is the purpose of `export default`?

It makes the component available to be used in other files.

### 6. What is the purpose of `import`?

It brings an exported component into the current file.

### 7. How do you use a component after importing it?

```jsx
<Welcome />
```

### 8. Explain the component flow.

```text
Create → Export → Import → Use → React Renders UI
```

---

This file should stay around **1.5–2 pages**, keeping it concise while still serving as both **study material** and a **last-minute revision sheet**. After this, your next file should be **`13_Component_Composition_and_Nesting.md`** (Parent-Child Relationship & Component Tree).
