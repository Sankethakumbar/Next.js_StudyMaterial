# JSX Advanced Concepts

## Topics Covered

1. JSX vs HTML
2. JSX Rules
3. Embedding JavaScript Expressions in JSX
4. Variables in JSX
5. Calculations in JSX
6. Function Calls in JSX
7. Conditional Rendering using Ternary Operator
8. Rendering Arrays using `map()`
9. Expressions vs Statements
10. JSX Must Have a Single Root Element
11. React Fragments
12. Common JSX Mistakes
13. JSX Practice Tasks
14. Quick Recap
15. Interview Questions

---

# JSX vs HTML

JSX looks very similar to HTML, but it is **not HTML**.

JSX is actually JavaScript syntax that gets converted into JavaScript code by Babel before the browser sees it.

Because JSX follows JavaScript rules, some HTML attributes have different names.

---

## Why JSX Has Differences

When you write JSX, React converts it into JavaScript using Babel.

Some HTML attribute names cannot be used directly because they conflict with JavaScript keywords or naming conventions.

Therefore, JSX uses slightly different names.

---

## Common JSX vs HTML Differences

| HTML        | JSX         | Reason                                |
| ----------- | ----------- | ------------------------------------- |
| `class`     | `className` | `class` is a JavaScript keyword.      |
| `for`       | `htmlFor`   | `for` is used in JavaScript loops.    |
| `onclick`   | `onClick`   | JSX uses camelCase naming.            |
| `tabindex`  | `tabIndex`  | Attributes use camelCase.             |
| `autofocus` | `autoFocus` | Follows JavaScript naming convention. |
| `<img>`     | `<img />`   | Empty tags must be self-closing.      |

---

## Example

HTML:

```html
<label for="email" class="box">
  Email
</label>
```

JSX:

```jsx
<label htmlFor="email" className="box">
  Email
</label>
```

---

# JSX Rules

When writing JSX, remember these important rules:

### Rule 1: JSX Must Have One Root Element

Every component should return one parent element.

### Rule 2: Use `className` Instead of `class`

```jsx
<div className="container">
  Hello
</div>
```

### Rule 3: Use `htmlFor` Instead of `for`

```jsx
<label htmlFor="email">
  Email
</label>
```

### Rule 4: Empty Tags Must Be Self-Closing

```jsx
<img src="/logo.png" />
<br />
<input />
```

### Rule 5: Attribute Names Use camelCase

Examples:

* `onClick`
* `tabIndex`
* `autoFocus`

### Rule 6: JavaScript Expressions Go Inside `{}`

```jsx
<h1>Hello {name}</h1>
```

---

# Embedding JavaScript Expressions in JSX

JSX allows you to combine JavaScript and UI code.

Anything written inside curly braces `{}` is treated as JavaScript.

This makes the UI dynamic because values can change automatically.

Example:

```jsx
const name = "Sanketha";

return <h1>Hello {name}</h1>;
```

---

# Variables in JSX

Variables can be displayed directly using `{}`.

Example:

```jsx
const name = "React";

export default function Home() {
  return (
    <h1>Welcome to {name}</h1>
  );
}
```

Output:

```text
Welcome to React
```

---

# Calculations in JSX

Simple mathematical and string operations can be performed inside `{}`.

Example:

```jsx
export default function Home() {
  return (
    <div>
      <p>5 + 10 = {5 + 10}</p>
      <p>20 × 3 = {20 * 3}</p>
    </div>
  );
}
```

Output:

```text
5 + 10 = 15
20 × 3 = 60
```

---

# Function Calls in JSX

Functions that return values can be called inside JSX.

Example:

```jsx
function greet() {
  return "Good Morning!";
}

export default function Home() {
  return (
    <h1>{greet()}</h1>
  );
}
```

Output:

```text
Good Morning!
```

---

# Conditional Rendering using Ternary Operator

JSX cannot directly use `if` statements inside `{}`, but it can use the ternary operator.

Syntax:

```javascript
condition ? value1 : value2
```

Example:

```jsx
const isLoggedIn = true;

export default function Home() {
  return (
    <h1>
      {isLoggedIn ? "Welcome Back!" : "Please Login"}
    </h1>
  );
}
```

Output when `isLoggedIn = true`:

```text
Welcome Back!
```

Output when `isLoggedIn = false`:

```text
Please Login
```

---

# Rendering Arrays using `map()`

React can display lists by using JavaScript array methods like `map()`.

Example:

```jsx
const fruits = ["Apple", "Mango", "Orange"];

export default function Home() {
  return (
    <ul>
      {fruits.map((fruit) => (
        <li>{fruit}</li>
      ))}
    </ul>
  );
}
```

Output:

```text
• Apple
• Mango
• Orange
```

The `map()` method loops through the array and creates a JSX element for each item.

---

# Expressions vs Statements

## What is an Expression?

An expression is any piece of JavaScript code that produces a value.

Examples:

* Variables
* Calculations
* Function calls
* Ternary operators

These can be used inside `{}`.

Example:

```jsx
<p>{10 + 20}</p>
<h1>{greet()}</h1>
```

---

## What is a Statement?

A statement performs an action but does not directly produce a value.

Examples:

* `if`
* `for`
* `while`
* `let`
* `const`

Statements cannot be used directly inside JSX.

❌ Invalid:

```jsx
<p>{if (age > 18) { "Adult" }}</p>
```

❌ Invalid:

```jsx
<p>{for(let i = 0; i < 5; i++) {}}</p>
```

---

## Simple Rule to Remember

> **If it returns a value, it can go inside `{}`. If it performs an action, it cannot.**

---

# JSX Must Have a Single Root Element

## Why JSX Needs One Root Element

Every React component must return one single parent (root) element.

This is because JSX is converted into JavaScript, and a JavaScript function can return only one value. React also uses this root element to build the Component Tree.

---

## Incorrect Example (❌)

```jsx
export default function Home() {
  return (
    <h1>Hello React</h1>
    <p>Welcome to JSX</p>
  );
}
```

This produces an error because there are two top-level elements.

---

## Correct: Wrap with a `<div>`

```jsx
export default function Home() {
  return (
    <div>
      <h1>Hello React</h1>
      <p>Welcome to JSX</p>
    </div>
  );
}
```

---

## Correct: Use React Fragments

```jsx
export default function Home() {
  return (
    <>
      <h1>Hello React</h1>
      <p>Welcome to JSX</p>
    </>
  );
}
```

Fragments allow grouping elements without adding an extra HTML element.

---

# React Fragments

A **React Fragment** (`<>...</>`) is a special wrapper that groups multiple JSX elements together without creating an extra DOM element.

## Why Use Fragments?

* Satisfy the single root element rule.
* Keep HTML output clean.
* Avoid unnecessary `<div>` wrappers.

---

## `<div>` vs Fragment

| `<div>`                      | Fragment (`<>...</>`)             |
| ---------------------------- | --------------------------------- |
| Creates a real HTML element. | Does not create any HTML element. |
| Can be styled using CSS.     | Used only for grouping.           |
| Useful for layouts.          | Useful for keeping the DOM clean. |

---

# Common JSX Mistakes

## 1. Using `class` instead of `className`

❌

```jsx
<div class="box"></div>
```

✅

```jsx
<div className="box"></div>
```

---

## 2. Using `for` instead of `htmlFor`

❌

```jsx
<label for="email">Email</label>
```

✅

```jsx
<label htmlFor="email">Email</label>
```

---

## 3. Forgetting Self-Closing Tags

❌

```jsx
<img>
```

✅

```jsx
<img />
```

---

## 4. Forgetting `{}` Around Variables

❌

```jsx
<h1>Hello name</h1>
```

✅

```jsx
<h1>Hello {name}</h1>
```

---

## 5. Using Statements Inside JSX

❌

```jsx
{if (x > 5) "Hello"}
```

Use a ternary operator instead.

---

## 6. Returning Multiple Root Elements

Always wrap sibling elements using a `<div>` or Fragment.


# Visual Summary

```text
JSX Rules
   │
   ├── Use className
   ├── Use htmlFor
   ├── Use camelCase attributes
   ├── Self-close empty tags
   ├── Use {} for JavaScript
   └── Return one root element


JavaScript in JSX
   │
   ├── Variables ✅
   ├── Calculations ✅
   ├── Function Calls ✅
   ├── Ternary Operators ✅
   ├── map() for Arrays ✅
   ├── if Statement ❌
   ├── for Loop ❌
   └── Variable Declarations ❌
```

---

# Quick Recap

## JSX vs HTML

JSX looks like HTML but follows JavaScript rules.

---

## Curly Braces `{}`

Used to embed JavaScript expressions inside JSX.

---

## Expressions

Variables, calculations, function calls, and ternary operators.

---

## Statements

`if`, `for`, `while`, `let`, and `const` cannot be used directly inside JSX.

---

## Single Root Element

Every component must return one parent element.

---

## React Fragments

Fragments group multiple elements without creating extra HTML.

---

# Interview Questions

## What is the difference between JSX and HTML?

JSX looks like HTML but is actually JavaScript syntax that gets converted into JavaScript by Babel.

---

## Why do we use `className` instead of `class`?

Because `class` is a reserved keyword in JavaScript.

---

## Why do we use `htmlFor` instead of `for`?

Because `for` is used in JavaScript loops.

---

## What can be written inside `{}` in JSX?

Variables, calculations, function calls, ternary operators, and other JavaScript expressions.

---

## What cannot be written inside `{}`?

Statements such as `if`, `for`, `while`, `let`, and `const`.

---

## What is the difference between an expression and a statement?

An expression produces a value, while a statement performs an action. JSX only accepts expressions.

---

## Why must JSX have a single root element?

Because React components return one JavaScript value, and React uses that root element to build the Component Tree.

---

## What is a React Fragment?

A Fragment is a wrapper that groups multiple JSX elements without adding an extra HTML element to the DOM.

---

## What is the difference between `<div>` and a Fragment?

A `<div>` creates a real HTML element, while a Fragment only groups elements and does not appear in the DOM.

---

## How do you render arrays in JSX?

Arrays are typically rendered using the JavaScript `map()` method.

---

## Complete the Rule:

```text
Inside { } we can use:
Variables ✔
Functions ✔
Calculations ✔
________ ✔
```

**Answer:**

```text
Ternary Operators
```

---

## Complete the Rule:

```text
Inside { } we cannot use:
if ❌
for ❌
while ❌
_______ ❌
```

**Answer:**

```text
let / const declarations
```

---

## Complete the JSX Flow:

```text
JSX
 ↓
Babel
 ↓
JavaScript
 ↓
React
 ↓
________
 ↓
Browser
```

**Answer:**

```text
Real DOM / HTML
```
