# Editing the Default Page

## Topics Covered

1. What is app/page.js?
2. Understanding the Home Component
3. Structure of a React Component
4. Editing the Default Page
5. Viewing Changes in the Browser
6. Hot Reloading
7. Creating New Routes Using page.js
8. Why page.js is Important
9. Quick Recap
10. Interview Questions

---

# What is app/page.js?

When a Next.js project is created using App Router, the file:

```text
app/page.js
```

acts as the default homepage of the application.

When users visit:

```text
http://localhost:3000
```

Next.js automatically loads and displays the UI defined inside:

```text
app/page.js
```

This file controls what appears on the Home Route (/).

---

# Understanding the Home Component

Example:

```javascript
export default function Home() {
  return (
    <h1>Hello Next.js!</h1>
  );
}
```

This code creates a React Component named Home.

The component returns UI that will be displayed inside the browser.

Everything returned from the component appears on the screen.

---

# Structure of a React Component

Example:

```javascript
export default function Home() {
  return (
    <h1>Hello Next.js!</h1>
  );
}
```

### export default

Makes the component available to Next.js.

Next.js automatically imports and displays this component.

---

### function Home()

A JavaScript function that acts as a React Component.

React components always start with a capital letter.

Examples:

```text
Home
Navbar
Footer
ProductCard
```

---

### return()

The return statement specifies what should be displayed on the screen.

Everything inside return becomes part of the UI.

---

### JSX

```jsx
<h1>Hello Next.js!</h1>
```

This looks like HTML but is actually JSX.

JSX allows developers to write HTML-like syntax inside JavaScript.

Later, Babel converts JSX into regular JavaScript.

---

# Editing the Default Page

Open:

```text
app/page.js
```

Replace the existing content:

```jsx
<h1>My First React Page</h1>
```

Example:

```javascript
export default function Home() {
  return (
    <h1>My First React Page</h1>
  );
}
```

Save the file.

---

# Viewing Changes in the Browser

After saving:

Open:

```text
http://localhost:3000
```

You will immediately see the updated content.

No manual refresh is required.

---

# Hot Reloading

Hot Reload is a feature provided by Next.js.

Whenever a file is saved:

```text
Save File
    ↓
Next.js Detects Change
    ↓
Rebuilds Component
    ↓
Browser Updates Automatically
```

Benefits:

* Faster development
* Immediate feedback
* No manual refresh required

---

# Try More Changes

Example:

```javascript
export default function Home() {
  return (
    <>
      <h1>My First React Page</h1>
      <p>This is my first React edit!</p>
    </>
  );
}
```

After saving, the browser automatically updates.

This allows developers to experiment and learn quickly.

---

# Creating New Routes Using page.js

In App Router, every route is created using a page.js file.

Example:

```text
app/
│
├── page.js
│
└── about/
    └── page.js
```

Routes:

```text
app/page.js
```

↓

```text
/
```

Homepage

---

```text
app/about/page.js
```

↓

```text
/about
```

About Page

This routing system is automatically handled by Next.js.

---

# Why page.js is Important

page.js is the entry point for a route.

It:

* Defines the UI of the route
* Contains React Components
* Is automatically detected by Next.js
* Creates pages without manual routing configuration

Without page.js, Next.js cannot render that route.

---

# Quick Recap

```text
app/page.js
       ↓
Defines Homepage UI

React Component
       ↓
Returns JSX

Save File
       ↓
Hot Reload

Browser
       ↓
Updates Automatically
```

---

# Interview Questions

## What is app/page.js?

The default page file used by Next.js App Router to render the homepage.

---

## Which route is controlled by app/page.js?

```text
/
```

(Home Route)

---

## What is the purpose of a React Component?

A React Component defines and returns UI that appears on the screen.

---

## What does return() do inside a component?

It specifies the UI that should be displayed in the browser.

---

## What is JSX?

JSX is a syntax extension that allows developers to write HTML-like code inside JavaScript.

---

## What happens when page.js is edited?

Next.js rebuilds the component and updates the browser automatically.

---

## What is Hot Reloading?

Hot Reloading automatically updates the browser whenever a file is saved.

---

## How do you create a new route in App Router?

Create a folder and add a page.js file inside it.

Example:

```text
app/about/page.js
```

creates:

```text
/about
```

---

## Why must React Components start with a capital letter?

React treats capitalized functions as Components and renders them as UI.

---

## Why is page.js important?

Because it defines the UI for a route and is automatically used by Next.js for rendering.
