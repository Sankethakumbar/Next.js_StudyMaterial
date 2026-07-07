# Conditional Rendering Fundamentals

## 📚 Topics Covered

- What is Conditional Rendering?
- Why do we need Conditional Rendering?
- if / else Rendering
- Ternary Operator (`? :`)
- Logical AND (`&&`)
- Returning `null`

---

# 📖 Definition

Conditional Rendering means **displaying different UI based on a condition**.

The condition usually depends on:

- State
- Props

React checks the condition and decides **what should be rendered on the screen**.

---

# 🤔 Why Do We Need Conditional Rendering?

Without Conditional Rendering:

- UI is static.
- Every user sees the same screen.

With Conditional Rendering:

- UI changes based on State or Props.
- Makes applications interactive and dynamic.

---

# 🧠 Mind Map

```text
State / Props
      │
      ▼
Condition
      │
      ├── True
      │      ▼
      │   Render UI A
      │
      └── False
             ▼
          Render UI B
```

---

# 🔄 Conditional Rendering Methods

React provides four common ways to conditionally render UI.

## 1️⃣ if / else

### Definition

Uses JavaScript's `if / else` statement to choose which JSX should be rendered.

### Syntax

```jsx
let content;

if (condition) {
    content = <ComponentA />;
} else {
    content = <ComponentB />;
}

return (
    <div>
        {content}
    </div>
);
```

### Best Used When

- Complex logic
- Multiple conditions
- Large JSX blocks

### Advantages

- Easy to understand
- Easy to debug
- Keeps JSX clean

---

## 2️⃣ Ternary Operator (`? :`)

### Definition

A shorter version of `if / else`.

### Syntax

```jsx
condition ? <ComponentA /> : <ComponentB />
```

### Best Used When

- Only two choices exist
- Small JSX
- Simple conditions

### Advantages

- Short
- Clean
- Works directly inside JSX

---

## 3️⃣ Logical AND (`&&`)

### Definition

Renders JSX **only when the condition is true**.

If the condition is false, React renders nothing.

### Syntax

```jsx
condition && <Component />
```

### Best Used When

- Show one element
- Hide one element
- No alternate UI is needed

### Advantages

- Very short
- Perfect for optional UI

---

## 4️⃣ return null

### Definition

Stops the component from rendering any UI.

The component still executes, but React displays nothing.

### Syntax

```jsx
if (!condition) {
    return null;
}

return <Component />;
```

### Best Used When

- Hide the entire component
- Permission-based rendering
- Feature flags

### Advantages

- Very clean
- Avoids unnecessary JSX

---

# 📊 Comparison Table

| Method | Best Used For |
|----------|----------------|
| if / else | Complex logic |
| Ternary (`? :`) | Two choices |
| Logical AND (`&&`) | Show or hide one element |
| return null | Hide entire component |

---

# ⚠ Common Mistakes

### ❌ Using `if` inside JSX

```jsx
return (
    <div>
        if(condition) {}
    </div>
)
```

Reason:

JSX accepts **expressions**, not **statements**.

---

### ❌ Using `&&` when two outputs are needed

Wrong:

```jsx
isLoggedIn && <Home />
```

Correct:

```jsx
isLoggedIn ? <Home /> : <Login />
```

---

### ❌ Using nested ternary operators

Avoid:

```jsx
condition1
    ? condition2
        ? A
        : B
    : C
```

Use `if / else` instead.

---

### ❌ Confusing `&&` with `return null`

Remember:

`&&` hides one JSX element.

`return null` hides the whole component.

---

# 🎯 When Should I Use Which?

```text
Need complex logic?
        │
     if / else

Need only two choices?
        │
      Ternary

Need to show or hide one element?
        │
          &&

Need to hide the whole component?
        │
      return null
```

---

# 📝 Quick Recap

- Conditional Rendering changes UI based on State or Props.
- `if / else` → Complex logic.
- Ternary → Two choices.
- `&&` → Show or hide one element.
- `return null` → Hide entire component.

---

# 💼 Interview Questions

- What is Conditional Rendering?
- Why do we use Conditional Rendering?
- Difference between `if / else` and Ternary?
- Difference between `&&` and Ternary?
- Difference between `&&` and `return null`?
- Why can't we use `if` inside JSX?
- What are expressions and statements?
- Which Conditional Rendering method would you use in different scenarios?