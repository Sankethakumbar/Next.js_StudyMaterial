# Advanced Props and `children`

## Topics Covered

1. Props are Read-Only
2. Why Props are Immutable
3. Component Reusability with Props
4. Passing JavaScript Expressions as Props
5. Component Composition with Props
6. The `children` Prop
7. How React Handles `children`
8. Wrapper Components
9. Props vs State (Preview)
10. Visual Summary
11. Quick Recap
12. Interview Questions

---

# Props are Read-Only

Props are **read-only**, which means a component can **use** the props it receives but **must never modify them**.

A parent component owns the data and passes it to its child components. The child component should only display or use that data.

❌ Incorrect:

```jsx
export default function User(props) {
  props.name = "Alex";
  return <h2>{props.name}</h2>;
}
```

✅ Correct:

```jsx
export default function User(props) {
  return <h2>{props.name}</h2>;
}
```

> **Rule:** A child component can read props, but it cannot change them.

---

# Why Props are Immutable

The word **immutable** means **cannot be changed**.

React keeps props immutable because it makes applications:

* More predictable
* Easier to debug
* Easier to maintain

If child components could change props, it would become difficult to know where and when data was modified.

---

# Component Reusability with Props

One of the biggest advantages of props is **reusability**.

Instead of creating many similar components, we create one component and pass different data through props.

Example:

```jsx
<Greeting name="Arya" />
<Greeting name="Sam" />
<Greeting name="John" />
```

The same `Greeting` component can now display different outputs without changing its code.

This helps reduce duplication and keeps the code clean.

---

# Passing JavaScript Expressions as Props

Props are not limited to text. React allows us to pass any JavaScript expression using curly braces `{}`.

Examples:

```jsx
<UserCard
  name="Arya"
  age={22}
  score={10 + 20}
  active={true}
/>
```

We can pass:

* Strings
* Numbers
* Booleans
* Variables
* Calculations
* Function results

Example:

```jsx
const username = "Arya";

<Greeting name={username} />
```

Curly braces tell React to evaluate the value as JavaScript before passing it.

---

# Component Composition with Props

**Component Composition** means building larger UI sections by combining smaller components.

Props help different components work together by passing data between them.

Example:

```text
Profile
   ├── UserName
   ├── UserBio
   └── UserButton
```

A larger `Profile` component can use many smaller components and pass props to each of them.

This keeps components:

* Small
* Reusable
* Easy to manage

---

# The `children` Prop

Sometimes we place content **inside** a component instead of passing it as a normal prop.

Example:

```jsx
<Card>
  <h2>Welcome!</h2>
  <p>This is my first card.</p>
</Card>
```

Everything between `<Card>` and `</Card>` automatically becomes a special prop called **`children`**.

> **Definition:** `children` is a special React prop that stores whatever is written inside a component's opening and closing tags.

---

# How React Handles `children`

When you write:

```jsx
<Card>
  <p>Hello React!</p>
</Card>
```

React internally treats it like this:

```jsx
<Card children={<p>Hello React!</p>} />
```

It automatically creates a props object similar to:

```javascript
props = {
  children: <p>Hello React!</p>
};
```

Inside the component, we can access it using:

```jsx
export default function Card(props) {
  return <div>{props.children}</div>;
}
```

or using destructuring:

```jsx
export default function Card({ children }) {
  return <div>{children}</div>;
}
```

Both approaches work exactly the same.

---

# Wrapper Components

A **Wrapper Component** is a component whose main job is to wrap and display other content.

The `children` prop makes wrapper components possible.

### Example

```jsx
export default function Card({ children }) {
  return (
    <div className="card">
      {children}
    </div>
  );
}
```

Using the component:

```jsx
<Card>
  <h2>React Study Material</h2>
  <p>Learning Props and Components.</p>
</Card>
```

The `Card` component stays the same, while the content inside it can change.

Common examples of wrapper components:

* Card
* Layout
* Container
* Modal
* Sidebar

---

# Props vs State (Preview)

Props and State are both used to manage data, but they have different purposes.

| Props                  | State                         |
| ---------------------- | ----------------------------- |
| Passed from Parent     | Managed inside the component  |
| Read-only              | Can be updated                |
| Used for communication | Used for local component data |

> **Remember:** Props come from outside the component, while State belongs to the component itself.

We will learn State in detail in the next chapter.

---

# Visual Summary

```text
               Parent Component
                      │
         ┌────────────┴────────────┐
         │                         │
         ▼                         ▼
   Passes Normal Props       Passes children
         │                         │
<Greeting name="Arya" />     <Card> ... </Card>
         │                         │
         ▼                         ▼
 props = { name: "Arya" }   props = { children: ... }
         │                         │
         └────────────┬────────────┘
                      ▼
              Child Component
                      │
                      ▼
                Displays UI
```

---

# Quick Recap

* Props are **read-only**.
* Child components should never modify props.
* Props are **immutable**.
* Props make components reusable.
* Curly braces `{}` allow us to pass JavaScript values and expressions.
* Component Composition means combining small components to build larger UI.
* `children` is a special prop that stores everything inside a component tag.
* Wrapper components use the `children` prop.
* Props and State are different; State will be learned later.

---

# Interview Questions

### 1. Are Props mutable or immutable?

Props are **immutable (read-only)** and should not be modified by child components.

---

### 2. Why are Props read-only?

Because the parent component owns the data. Keeping props immutable makes React applications predictable and easier to debug.

---

### 3. How do Props improve reusability?

The same component can be used multiple times with different prop values, producing different outputs.

---

### 4. Can we pass JavaScript expressions as Props?

Yes. We can pass variables, numbers, booleans, calculations, and other JavaScript expressions using curly braces `{}`.

Example:

```jsx
<UserCard score={10 + 20} />
```

---

### 5. What is Component Composition?

Component Composition is the process of combining smaller components to build larger and more complex UI sections.

---

### 6. What is the `children` prop?

`children` is a special React prop that automatically contains everything written between a component's opening and closing tags.

---

### 7. How does React internally handle this?

```jsx
<Card>
  <p>Hello</p>
</Card>
```

**Answer:**

React internally treats it like:

```jsx
<Card children={<p>Hello</p>} />
```

---

### 8. What is a Wrapper Component?

A wrapper component is a component that surrounds and displays other content using the `children` prop.

Examples: Card, Layout, Modal.

---

### 9. What is the difference between Props and State?

| Props              | State                |
| ------------------ | -------------------- |
| Passed from Parent | Managed by Component |
| Read-only          | Can change           |
| External Data      | Internal Data        |

---

### 10. Complete the Statement:

```text
Everything written between
<Component> ... </Component>
becomes __________.
```

**Answer:**

```text
props.children
```

---

### 11. Complete the Flow:

```text
<Card>
   <h2>Hello</h2>
</Card>

        ↓

React Creates

props = {
   __________
}
```

**Answer:**

```text
children: <h2>Hello</h2>
```

---

## 📌 Memory Sheet

```text
Props = Read-Only
Parent Owns the Data
Child Only Uses the Data

Props → Reusability
Props → Component Communication

Curly Braces {} → JavaScript Values

Component Composition
= Build Big Components
  Using Small Components

<Card>
   Content
</Card>

        ↓

props.children

children = Everything Inside the Tags

Props → External Data
State → Internal Data
```

---

## 💡 Easy Way to Remember `children`

Think of a component like a **box**.

```text
<Card>
   🎁 Any JSX goes here
</Card>
```

React automatically puts everything inside the box into a special prop called **`children`**.

```text
<Component> ... </Component>
           ↓
     props.children
```

You don't create the `children` prop yourself—**React creates it automatically.**
