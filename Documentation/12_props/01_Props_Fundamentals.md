# Props Fundamentals

## Topics Covered

1. What are Props?
2. Why Do We Need Props?
3. Props as Function Arguments
4. Passing Props
5. The Props Object
6. Accessing Props
7. Destructuring Props
8. Multiple Props
9. Strings vs Curly Braces
10. One-Way Data Flow
11. Visual Summary
12. Quick Recap
13. Interview Questions

---

# What are Props?

**Props** stands for **Properties**.

Props are **inputs given to a component**. They allow us to pass data from one component to another.

In React, data is usually passed from a **Parent Component** to a **Child Component** using props.

> **Simple Definition:** Props are a way to send data to a component.

---

# Why Do We Need Props?

Without props, every component would always display the same fixed data.

Props make components:

* ♻️ Reusable
* 🔄 Dynamic
* 🧩 Flexible

For example, instead of creating three separate greeting components, we can create one `Greeting` component and pass different names using props.

```jsx
<Greeting name="Arya" />
<Greeting name="Sam" />
<Greeting name="John" />
```

The same component produces different output depending on the props it receives.

---

# Props as Function Arguments

A React component is simply a JavaScript function.

Just as we pass arguments to a normal JavaScript function, we pass props to a React component.

JavaScript function:

```javascript
function greet(name) {
  return "Hello " + name;
}

greet("Arya");
```

React component:

```jsx
<Greeting name="Arya" />
```

You can think of props as the arguments that React automatically passes to a component.

---

# Passing Props

Props are passed to a component just like HTML attributes.

Example:

```jsx
<Greeting name="Arya" />
```

Here:

* `name` → Prop Name
* `"Arya"` → Prop Value

You can create any prop you need:

```jsx
<UserCard
  name="Arya"
  age={22}
  city="Delhi"
/>
```

---

# The Props Object

React collects all the props and stores them inside a single object called `props`.

If we write:

```jsx
<Greeting name="Arya" />
```

React internally creates something similar to:

```javascript
props = {
  name: "Arya"
};
```

If we pass multiple props:

```jsx
<UserCard
  name="Arya"
  age={22}
  city="Delhi"
/>
```

React creates:

```javascript
props = {
  name: "Arya",
  age: 22,
  city: "Delhi"
};
```

You do not create this object yourself—React automatically creates and passes it to the component.

---

# Accessing Props

The simplest way to read a prop is by using:

```text
props.propName
```

Example:

### `components/Greeting.js`

```jsx
export default function Greeting(props) {
  return <h2>Hello, {props.name}!</h2>;
}
```

### `app/page.js`

```jsx
import Greeting from "../components/Greeting";

export default function Page() {
  return (
    <div>
      <Greeting name="Arya" />
    </div>
  );
}
```

Here:

* React passes `name="Arya"`.
* React creates `props = { name: "Arya" }`.
* `props.name` gives the value `"Arya"`.

---

# Destructuring Props

Destructuring is simply a shorter and cleaner way to access values from the props object.

Instead of writing:

```jsx
export default function Greeting(props) {
  return <h2>Hello, {props.name}!</h2>;
}
```

We can write:

```jsx
export default function Greeting({ name }) {
  return <h2>Hello, {name}!</h2>;
}
```

This works because:

```javascript
const { name } = props;
```

Both methods are correct. Destructuring is commonly used because it reduces repetition.

---

# Multiple Props

A component can receive more than one prop at the same time.

Example:

```jsx
<UserCard
  name="Arya"
  age={22}
  city="Delhi"
/>
```

The component can access all these values:

```jsx
export default function UserCard({ name, age, city }) {
  return (
    <div>
      <h3>{name}</h3>
      <p>Age: {age}</p>
      <p>City: {city}</p>
    </div>
  );
}
```

This allows one component to display different information without changing the component itself.

---

# Strings vs Curly Braces

When passing props, you may notice two different styles.

### Strings use Quotes (`" "`)

```jsx
<Greeting name="Arya" />
```

Quotes tell React that the value is plain text (a string).

---

### JavaScript Values use Curly Braces (`{ }`)

```jsx
<UserCard age={22} />
```

Curly braces tell React:

> "Treat this as a JavaScript expression."

You should use `{}` for:

* Numbers
* Variables
* Booleans
* Calculations
* JavaScript expressions

Examples:

```jsx
<UserCard
  name="Arya"
  age={22}
  active={true}
  score={10 + 20}
/>
```

| Data Type  | Example           |
| ---------- | ----------------- |
| String     | `name="Arya"`     |
| Number     | `age={22}`        |
| Boolean    | `active={true}`   |
| Variable   | `name={userName}` |
| Expression | `score={10 + 20}` |

---

# One-Way Data Flow

React follows **One-Way Data Flow** (also called **Unidirectional Data Flow**).

This means data always moves:

```text
Parent Component
        │
        │ Props
        ▼
Child Component
```

The **Parent Component** passes props to the **Child Component**, and the child uses that data to display the UI.

A child component cannot directly send props back to its parent.

> **Simple Rule:** Data flows from **Parent → Child**.

---

# Visual Summary

```text
Parent Component
        │
        │ Passes Props
        ▼
<Greeting name="Arya" />
        │
        ▼
React Creates

props = {
   name: "Arya"
}

        │
        ▼
Child Component

props.name
or
{ name }

        │
        ▼
Displays:
Hello, Arya!
```

---

# Quick Recap

* Props stands for **Properties**.
* Props are inputs given to a component.
* Props allow data to move from Parent → Child.
* Props are passed like HTML attributes.
* React collects all props into a `props` object.
* Access props using `props.propName`.
* Destructuring (`{ name }`) is a shorter way to read props.
* A component can receive multiple props.
* Strings use quotes (`" "`), while JavaScript values use curly braces (`{ }`).
* React follows **One-Way Data Flow**.

---

# Interview Questions

### 1. What are Props in React?

Props (Properties) are inputs given to a component that allow data to be passed from a Parent Component to a Child Component.

---

### 2. Why do we use Props?

Props make components reusable, dynamic, and flexible by allowing them to display different data.

---

### 3. How are Props passed to a component?

Props are passed as attributes inside the component tag.

Example:

```jsx
<Greeting name="Arya" />
```

---

### 4. What is the `props` object?

The `props` object is automatically created by React and contains all the props passed to a component.

---

### 5. How do you access a prop inside a component?

You can access it using:

```text
props.propName
```

Example:

```jsx
props.name
```

---

### 6. What is destructuring in React?

Destructuring is a shorter way of extracting values from the `props` object.

Example:

```jsx
function Greeting({ name }) {
  return <h1>{name}</h1>;
}
```

---

### 7. Can a component receive multiple props?

Yes. A component can receive any number of props.

Example:

```jsx
<UserCard
  name="Arya"
  age={22}
  city="Delhi"
/>
```

---

### 8. Why do strings use quotes while numbers use curly braces?

* Quotes (`" "`) represent text (strings).
* Curly braces (`{ }`) tell React to evaluate a JavaScript expression.

---

### 9. What is One-Way Data Flow?

One-Way Data Flow means data always moves from the Parent Component to the Child Component through props.

---

### 10. Complete the Flow:

```text
Parent Component
        ↓
    __________
        ↓
Child Component
```

**Answer:**

```text
Props
```

---

### 11. Complete the Statement:

```text
Props are stored inside the __________ object.
```

**Answer:**

```text
props
```

---

### 12. Complete the Table:

| Syntax        | Data Type |
| ------------- | --------- |
| `name="Arya"` | ?         |
| `age={22}`    | ?         |

**Answer:**

| Syntax        | Data Type         |
| ------------- | ----------------- |
| `name="Arya"` | String            |
| `age={22}`    | JavaScript Number |

---

## 📌 Memory Sheet

```text
Props = Properties
Props = Inputs to a Component

Parent
   │
   │ Props
   ▼
Child

Props → Passed like HTML attributes
React → Creates a props object
props.name → Access value
{ name } → Destructuring

"Hello" → String
{22} → JavaScript Value

One-Way Data Flow:
Parent → Child
```

This file is enough for the **fundamentals**. The **second file** will naturally continue with:

* Props are Read-Only
* Why Props are Immutable
* Reusability with Props
* Component Composition
* `children` Prop
* Wrapper Components
* Props vs State (preview)
* Interview Questions & Practice Tasks.
