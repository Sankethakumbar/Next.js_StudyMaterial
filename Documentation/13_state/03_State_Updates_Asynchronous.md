# State Updates Are Asynchronous

## Topics Covered

1. What Does Asynchronous Mean?
2. Why React Updates State Later
3. Why Direct Assignment Doesn't Work
4. The Console.log Confusion
5. Multiple State Updates Problem
6. Functional Updates
7. What Does `prev` Represent?
8. When to Use Functional Updates
9. Quick Recap
10. Interview Questions

---

# What Does Asynchronous Mean?

When we call a setter function:

```jsx
setCount(count + 1);
```

React does **not update the state immediately**.

Instead:

```text
Setter Called
      ↓
React Stores Update
      ↓
Component Finishes Execution
      ↓
React Updates State
      ↓
Re-render Happens
```

This behavior is called **Asynchronous State Updates**.

---

# Why React Updates State Later

React batches multiple state updates together before re-rendering.

Benefits:

- Better Performance
- Fewer Re-renders
- Faster UI Updates

Instead of:

```text
Update
Render

Update
Render
```

React does:

```text
Update
Update
Update
      ↓
Single Re-render
```

This process is called **Batching**.

---

# Why Direct Assignment Doesn't Work

❌ Wrong

```jsx
count = count + 1;
```

Why?

- Does not update React state
- Does not notify React about the change
- Does not trigger a re-render
- UI will not update

React only tracks changes made through setter functions.

✅ Correct

```jsx
setCount(count + 1);
```

Flow:

```text
Setter Called
      ↓
React Updates State
      ↓
React Re-renders Component
      ↓
UI Updates
```

---

# The Console.log Confusion

Example:

```jsx
function handleClick() {
  setCount(count + 1);
  console.log(count);
}
```

Suppose:

```jsx
count = 0;
```

Output:

```text
0
```

Not:

```text
1
```

Why?

Because React has not updated the state yet.

The event handler still sees the old value.

---

# What is a Setter Function?

When we use:

```jsx
const [count, setCount] = useState(0);
```

The `useState` hook returns two values:

```text
Current State Value
        +
Setter Function
```

Here:

```jsx
count
```

→ Current state value

```jsx
setCount
```

→ Setter function returned by `useState`

Purpose:

- Updates a specific state variable
- Tells React that state changed
- Triggers a re-render
- Updates the UI automatically

---

# Multiple State Updates Problem

Example:

```jsx
setCount(count + 1);
setCount(count + 1);
```

Current value:

```jsx
count = 0;
```

React receives:

```jsx
setCount(1);
setCount(1);
```

Final result:

```text
1
```

Not:

```text
2
```

Because both updates use the same old value.

---

# Functional Updates

When the next state depends on the previous state, use:

```jsx
setCount(prev => prev + 1);
```

Example:

```jsx
setCount(prev => prev + 1);
setCount(prev => prev + 1);
```

React processes them one by one:

```text
prev = 0
↓
1

prev = 1
↓
2
```

Final result:

```text
2
```

---

# What Does `prev` Represent?

Example:

```jsx
setCount(prev => prev + 1);
```

`prev` represents:

```text
Latest State Value Managed By React
```

React automatically provides this value.

Meaning:

```text
Take Current State
       ↓
Add 1
       ↓
Store New State
```

Important:

```text
prev ≠ count variable

prev = latest state value maintained internally by React
```

---

# Why Functional Updates Work

With:

```jsx
setCount(count + 1);
```

React uses the old value stored in `count`.

With:

```jsx
setCount(prev => prev + 1);
```

React uses the latest state value available internally.

That's why:

```jsx
setCount(prev => prev + 1);
setCount(prev => prev + 1);
```

works correctly and gives:

```text
2
```

---

# When to Use Functional Updates

Use Functional Updates whenever the next state depends on the previous state.

### Counter

```jsx
setCount(prev => prev + 1);
```

### Decrement

```jsx
setCount(prev => prev - 1);
```

### Toggle

```jsx
setIsOpen(prev => !prev);
```

### Like Counter

```jsx
setLikes(prev => prev + 1);
```

---

# Quick Recap

## Asynchronous State

React does not update state immediately.

---

## Batching

React groups multiple updates together for performance.

---

## Direct Assignment

❌ Wrong

```jsx
count = count + 1;
```

Does not update React state or trigger re-render.

---

## Setter Function

Returned by `useState`.

Used to update state and trigger re-render.

---

## Console.log

May show the old value immediately after calling a setter.

---

## Functional Updates

Use:

```jsx
setCount(prev => prev + 1);
```

when the next state depends on the previous state.

---

## prev

Represents the latest state value managed by React.

---

# Interview Questions

### What does it mean that state updates are asynchronous?

### Why doesn't React update state immediately?

### What is batching in React?

### Why should state never be updated directly?

### Why does direct assignment not update the UI?

### What is the purpose of the setter function returned by useState?

### What does useState return?

### Why does this print the old value?

```jsx
setCount(count + 1);
console.log(count);
```

### What is the difference between:

```jsx
setCount(count + 1);
```

and

```jsx
setCount(prev => prev + 1);
```

### Why does this increase only once?

```jsx
setCount(count + 1);
setCount(count + 1);
```

### What is a functional update?

### What does the parameter `prev` represent?

### Why are functional updates needed?

### When should functional updates be used?

### Which is safer for counters?

```jsx
count + 1
```

or

```jsx
prev => prev + 1
```

---

# One-Line Revision

```text
State updates are asynchronous and batched by React. Never update state directly. Always use the setter function returned by useState. When the next state depends on the previous state, use:

setState(prev => newValue)
```

---

# Memory Trick

```text
Need Previous Value?
        ↓
Use prev

setCount(prev => prev + 1)
```