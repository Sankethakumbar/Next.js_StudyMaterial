
# JSX Fundamentals

## Topics Covered

1. What is JSX?
2. Why Was JSX Introduced?
3. React Without JSX (`React.createElement()`)
4. JSX vs `React.createElement()`
5. What Does `render()` Do?
6. JSX in a Real Next.js Component
7. How JSX Works Behind the Scenes
8. What is Babel?
9. How Babel Compiles JSX
10. JSX Rendering Flow
11. Why JSX is Better
12. Quick Recap
13. Interview Questions

---

# What is JSX?

JSX stands for:

```text
JavaScript XML
```

JSX is a syntax extension for JavaScript that allows developers to write HTML-like code inside JavaScript files.

Example:

```jsx
<h1>Hello React</h1>
```

Although JSX looks like HTML, it is **not HTML**. It is special syntax that React understands and later converts into JavaScript.

JSX is not a string and browsers cannot understand it directly.

---

# Why Was JSX Introduced?

Before JSX, React developers built UI using JavaScript function calls.

Example:

```javascript
React.createElement(
  "h1",
  null,
  "Hello React"
);
```

As applications grew larger, these nested function calls became difficult to read and maintain.

JSX was introduced to solve this problem.

Benefits of JSX:

* Easier to read
* Easier to write
* Easier to debug
* Makes UI structure more visual
* Encourages component-based development

---

# React Without JSX (`React.createElement()`)

React provides a built-in function called `React.createElement()`.

It creates React Elements, which are JavaScript objects that describe the UI.

Example:

```javascript
const heading = React.createElement(
  "h1",
  null,
  "Hello React"
);
```

Here:

* `"h1"` → Element type
* `null` → No attributes (props)
* `"Hello React"` → Content inside the element

This is equivalent to:

```html
<h1>Hello React</h1>
```

---

## Creating Nested Elements

Suppose we want to create:

```html
<div>
  <h1>Welcome</h1>
  <p>This is a paragraph</p>
</div>
```

Without JSX:

```javascript
const element = React.createElement(
  "div",
  null,
  React.createElement(
    "h1",
    null,
    "Welcome"
  ),
  React.createElement(
    "p",
    null,
    "This is a paragraph"
  )
);
```

As the UI grows, the structure becomes deeply nested and difficult to understand.

---

# JSX vs `React.createElement()`

| JSX                           | React.createElement()          |
| ----------------------------- | ------------------------------ |
| HTML-like syntax              | Nested function calls          |
| Easy to read                  | Hard to read                   |
| Easy to maintain              | Difficult to debug             |
| Better for large applications | Becomes complex for nested UIs |

Visual Comparison:

```text
JSX:                        Without JSX:

<div>                       React.createElement(
  <h1>Welcome</h1>            "div",
  <p>Hello</p>                null,
</div>                        React.createElement(
                                 "h1", null, "Welcome"
                              ),
                              React.createElement(
                                 "p", null, "Hello"
                              )
                            )
```

JSX provides much better visual clarity.

---

# What Does `render()` Do?

Creating React elements alone does not display them on the screen.

The `render()` process tells React:

> "Take this UI and display it inside a specific part of the webpage."

In older React versions, rendering looked like this:

```javascript
ReactDOM.render(
  element,
  document.getElementById("root")
);
```

Where:

* `element` → UI created using `React.createElement()`
* `document.getElementById("root")` → Target container in the HTML page

---

## How Rendering Works in Next.js

In Next.js, developers do not manually call `render()`.

When you return JSX from a component like `page.js`, Next.js automatically renders that UI in the browser.

This allows developers to focus on **what to display**, while Next.js handles **how to display it**.

---

# JSX in a Real Next.js Component

Example:

```jsx
export default function Home() {
  return (
    <div>
      <h1>Hello React</h1>
      <p>Learning JSX is fun!</p>
    </div>
  );
}
```

In this example:

* `export default` makes the component available to Next.js.
* `function Home()` defines a React Functional Component.
* `return()` specifies the UI to display.
* Everything inside `return()` is JSX.

Whenever you open `app/page.js`, the code inside the `return()` block is JSX.

---

# How JSX Works Behind the Scenes

Browsers understand:

* HTML
* CSS
* JavaScript

Browsers **do not understand JSX**.

Therefore JSX must first be converted into JavaScript.

Flow:

```text
Developer Writes JSX
          ↓
Babel
          ↓
React.createElement()
          ↓
React Elements
          ↓
Virtual DOM
          ↓
Real DOM
          ↓
Browser UI
```

---

# What is Babel?

Babel is a **JavaScript Compiler**.

Its job is to convert:

* JSX into JavaScript.
* Modern JavaScript into browser-compatible JavaScript.

Example:

JSX:

```jsx
<h1>Hello React</h1>
```

Babel converts it into:

```javascript
React.createElement(
  "h1",
  null,
  "Hello React"
);
```

---

## Why Babel is Needed

Different browsers support JavaScript features differently.

Babel ensures that the code works consistently across all major browsers.

Responsibilities of Babel:

* Convert JSX.
* Convert modern JavaScript.
* Improve browser compatibility.
* Help React applications run everywhere.

---

## Babel in Next.js

Next.js comes with **Babel pre-installed and pre-configured**.

Developers do not need to install or configure Babel manually.

Every time you save a JSX file, Next.js automatically runs Babel behind the scenes.

---

# How Babel Compiles JSX

The JSX code:

```jsx
<h1>Hello React</h1>
```

is transformed into:

```javascript
React.createElement(
  "h1",
  null,
  "Hello React"
);
```

Then React converts these React Elements into actual DOM elements displayed by the browser.

Simple Flow:

```text
JSX
 ↓
Babel
 ↓
React.createElement()
 ↓
React Elements
 ↓
HTML on Screen
```

---

# JSX Rendering Flow

Complete flow from code to browser:

```text
Developer Writes JSX
           ↓
Babel
           ↓
Converts JSX to JavaScript
           ↓
React.createElement()
           ↓
React Creates React Elements
           ↓
Virtual DOM
           ↓
Diffing & Reconciliation
           ↓
Real DOM Updated
           ↓
Browser Displays UI
```

---

# Why JSX is Better

Compared to writing UI using `React.createElement()`, JSX offers several advantages:

* Cleaner syntax.
* Less nested code.
* Easier debugging.
* Better readability.
* Feels similar to writing HTML.
* Makes component structures easier to visualize.
* Encourages reusable UI components.

This is why almost all modern React applications use JSX instead of manually calling `React.createElement()`.

---

# Quick Recap

## JSX

HTML-like syntax written inside JavaScript.

---

## React.createElement()

Creates React Elements using JavaScript function calls.

---

## render()

Displays React elements inside the webpage.

(Automatically handled by Next.js.)

---

## Babel

Converts JSX and modern JavaScript into browser-friendly JavaScript.

---

## JSX Flow

```text
JSX
 ↓
Babel
 ↓
React.createElement()
 ↓
React Elements
 ↓
Virtual DOM
 ↓
Real DOM
 ↓
Browser UI
```

---

## Why JSX?

* Easier to read.
* Easier to write.
* Easier to maintain.
* Better for building complex UIs.

---

# Interview Questions

## What is JSX?

JSX (JavaScript XML) is a syntax extension that allows developers to write HTML-like code inside JavaScript.

---

## Is JSX HTML?

No. JSX only looks like HTML. It is converted into JavaScript by Babel.

---

## Why was JSX introduced?

JSX was introduced to make UI code easier to read, write, and maintain compared to nested `React.createElement()` calls.

---

## What is `React.createElement()`?

It is a React function that creates React Elements (JavaScript objects representing the UI).

---

## Why is `React.createElement()` difficult to use for large UIs?

Because nested function calls become deeply nested and difficult to read and maintain.

---

## What does `render()` do?

`render()` displays React elements inside a DOM container. In Next.js, rendering is handled automatically.

---

## What is Babel?

Babel is a JavaScript compiler that converts JSX and modern JavaScript into browser-compatible JavaScript.

---

## Why can't browsers understand JSX directly?

Because JSX is not standard JavaScript and must first be converted by Babel.

---

## How does JSX become HTML?

```text
JSX
 ↓
Babel
 ↓
React.createElement()
 ↓
React Elements
 ↓
Virtual DOM
 ↓
Real DOM
 ↓
Browser UI
```

---

## What is the role of Babel in Next.js?

Next.js uses Babel to automatically compile JSX and modern JavaScript into browser-friendly JavaScript.

---

## Complete the Flow:

```text
JSX
 ↓
________
 ↓
React.createElement()
 ↓
React Elements
```

**Answer:**

```text
Babel
```

---

## Complete the Flow:

```text
Developer Writes JSX
           ↓
Babel
           ↓
________
           ↓
Virtual DOM
```

**Answer:**

```text
React.createElement()
```
