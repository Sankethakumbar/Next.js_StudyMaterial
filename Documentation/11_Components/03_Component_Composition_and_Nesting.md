# Component Composition and Nesting

## Topics Covered

1. What is Component Composition?
2. What is Nesting?
3. Parent and Child Components
4. Why Do We Nest Components?
5. Building the Component Tree
6. Multi-Level Nesting
7. Avoid Over-Nesting
8. Visual Summary
9. Quick Recap
10. Interview Questions

---

# What is Component Composition?

**Component Composition** means building a larger UI by combining smaller components.

Instead of writing one big component, we create many small components and assemble them together.

> **Simple Idea:** Small components + Combined together = Complete Application.

---

# What is Nesting?

**Nesting** means placing one component inside another component.

Example:

```jsx
<div>
  <Navbar />
  <Footer />
</div>
```

Here, `Navbar` and `Footer` are nested inside the parent component.

---

# Parent and Child Components

When one component is used inside another:

* The outer component is called the **Parent**.
* The inner component is called the **Child**.

Example:

```jsx
export default function Page() {
  return (
    <div>
      <Navbar />
    </div>
  );
}
```

* `Page` → Parent
* `Navbar` → Child

> **Rule:** The relationship depends on where the component is used.

---

# Why Do We Nest Components?

Nesting helps us:

* ♻️ Reuse components easily.
* 🧩 Break the UI into small manageable parts.
* 🛠️ Keep code clean and organized.
* 🐞 Make debugging easier.

Think of nesting like building with **LEGO blocks**—small blocks combine to build bigger structures.

---

# Building the Component Tree

When components are nested, React organizes them into a **Component Tree**.

Example:

```text
App
│
├── Navbar
├── MainContent
│     ├── Card
│     ├── Card
│     └── Card
└── Footer
```

Each component can contain more child components, creating a tree-like structure.

---

# Multi-Level Nesting

Components can be nested inside other components multiple levels deep.

Example:

```text
Page
│
└── Layout
      │
      ├── Header
      ├── Content
      └── Footer
```

Here:

* `Page` is the parent of `Layout`.
* `Layout` is the parent of `Header`, `Content`, and `Footer`.
* `Header`, `Content`, and `Footer` are children of `Layout`.

---

# Simple Working Example

### `components/Navbar.js`

```jsx
export default function Navbar() {
  return <h2>My Website</h2>;
}
```

### `app/page.js`

```jsx
import Navbar from "../components/Navbar";

export default function Page() {
  return (
    <div>
      <Navbar />
      <p>Welcome to the homepage!</p>
    </div>
  );
}
```

React combines these components to create the final UI.

---

# Avoid Over-Nesting

While nesting is useful, too many levels can make code difficult to read.

❌ Bad:

```text
App
└── Layout
     └── Wrapper
          └── Container
               └── Section
                    └── Card
```

✅ Better:

Keep components focused and avoid unnecessary wrapper components.

> **Rule:** Create small components, but don't create components for everything.

---

# Visual Summary

```text
React App
    │
    ├── Parent Component
    │        │
    │        ├── Child Component
    │        └── Child Component
    │
    └── Footer Component
```

```text
Small Components
        ↓
Component Composition
        ↓
Component Tree
        ↓
Complete UI
```

---

# Quick Recap

* **Component Composition** means combining small components to build larger UIs.
* **Nesting** means placing one component inside another.
* The outer component is the **Parent** and the inner one is the **Child**.
* Nested components form a **Component Tree**.
* React applications are built by composing many small reusable components.
* Avoid excessive nesting to keep code clean.

---

# Interview Questions

### 1. What is Component Composition?

Component Composition is the process of combining smaller components to build a complete UI.

### 2. What is Component Nesting?

Nesting means using one component inside another component.

### 3. What is the difference between a Parent and Child Component?

The component that contains another component is the **Parent**, and the contained component is the **Child**.

### 4. How does React decide the Parent–Child relationship?

It depends on where components are used. If `<Navbar />` is inside `Page`, then `Page` is the parent and `Navbar` is the child.

### 5. What is a Component Tree?

A hierarchical structure showing how components are connected through parent-child relationships.

### 6. Why do we use Component Composition?

To improve reusability, maintainability, and code organization.

### 7. What are the benefits of Nesting?

* Reusable UI
* Cleaner code
* Easier debugging
* Better organization

### 8. Complete the Flow:

```text
Small Components
       ↓
________________
       ↓
Component Tree
       ↓
Complete UI
```

**Answer:**

```text
Component Composition
```

### 9. Complete the Relationship:

```text
<Page>
   <Navbar />
</Page>
```

**Answer:**

* `Page` → Parent Component
* `Navbar` → Child Component

---

## 📌 One-Line Memory Trick

```text
Component = One UI block
Nesting = Putting components inside components
Composition = Combining many components to build the final UI
Parent → Contains Child
Child → Lives inside Parent
```
