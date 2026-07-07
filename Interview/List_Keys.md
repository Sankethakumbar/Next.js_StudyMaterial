# 🎯 Lists & Keys Interview Handbook

---

# ⭐⭐⭐⭐⭐ Must Remember

```text
Array
  │
  ▼
map()
  │
  ▼
JSX
  │
  ▼
React Renders
```

```text
Keys
 │
 ▼
Unique
 │
 ▼
Track Items
 │
 ▼
Reconciliation
 │
 ▼
Efficient Updates
```

---

# ⭐⭐⭐⭐⭐ Top 10 Interview Questions

## 1. What is List Rendering?

### One-Line Answer

Displaying multiple UI elements by iterating over an array using `map()`.

🧠 Mind Map

```text
Array
 │
 ▼
map()
 │
 ▼
JSX
 │
 ▼
UI
```

---

## 2. Why use map()?

✔ Less Code

✔ Dynamic UI

✔ Readable

✔ Reusable

🧠 Memory Trick

```text
Array
 ↓
Transform
 ↓
JSX
 ↓
Render
```

---

## 3. Does map() render the UI?

❌ No

```text
map()

↓

Creates JSX

↓

React

↓

Renders UI
```

---

## 4. What does map() return?

✔ New Array

React

↓

Array of JSX

---

## 5. Difference

| map() | forEach() |
|--------|-----------|
| Returns Array | Returns undefined |
| Rendering | Side Effects |
| React | JavaScript |

---

# ⭐⭐⭐⭐⭐ Keys

## 6. What are Keys?

One-Line

Unique identifiers used by React to track list items.

🧠 Mind Map

```text
Keys
 │
 ▼
Unique
 │
 ▼
Track
 │
 ▼
Update
```

---

## 7. Why do we need Keys?

Without Keys

```text
Old List

↓

Compare Position

↓

More Work
```

With Keys

```text
Old List

↓

Compare Keys

↓

Exact Item Found

↓

Update
```

---

## 8. What is Reconciliation?

One-Line

React compares the previous Virtual DOM with the new Virtual DOM and updates only the changed elements.

🧠 Mind Map

```text
Old VDOM

↓

New VDOM

↓

Compare

↓

Update DOM
```

---

## 9. Why not Index?

```text
Old

0 Apple

1 Banana

2 Orange
```

Insert Mango

```text
0 Mango

1 Apple

2 Banana

3 Orange
```

Index changes

↓

React thinks

↓

Everything changed ❌

---

## 10. When can Index be used?

```text
Static List

↓

No Add

↓

No Delete

↓

No Sort

↓

No Filter
```

---

# ⭐⭐⭐⭐⭐ Good vs Bad Keys

## ✅ Good

```text
✔ ID

✔ UUID

✔ Email

✔ Username
```

---

## ❌ Bad

```text
❌ Index

❌ Math.random()

❌ Date.now()
```

---

# ⭐⭐⭐⭐⭐ Edge Cases

❓ Can key be duplicate?

❌ No (among siblings)

---

❓ Can we access key using props?

❌ No

Reserved by React

---

❓ Can different lists have same keys?

✔ Yes

Only siblings need unique keys.

---

# ⭐⭐⭐⭐ Extracting Components

```text
Large JSX

↓

Extract

↓

Component

↓

Reusable
```

Advantages

✔ Readable

✔ Reusable

✔ Maintainable

---

# ⭐⭐⭐⭐ Empty List

```text
Array Empty?

     │

 ┌───┴────┐

Yes       No

 │         │

 ▼         ▼

Fallback  map()
```

Example

```jsx
items.length === 0
    ? <p>No Data</p>
    : displayItems
```

---

# ⭐⭐⭐⭐⭐ Common Mistakes

❌ Forgetting key

❌ Using index

❌ Using Math.random()

❌ Thinking map() renders UI

❌ Returning component inside itself

```jsx
<StudentPortal />
```

Infinite recursion ❌

---

# ⭐⭐⭐⭐⭐ Coding Pattern

```text
Array

↓

map()

↓

key

↓

JSX

↓

Conditional Rendering

↓

Fallback UI
```

---

# ⭐⭐⭐⭐⭐ 2-Minute Revision

```text
List Rendering

↓

map()

↓

New Array

↓

JSX

↓

React
```

---

```text
Keys

↓

Unique

↓

Stable

↓

Track Items

↓

Reconciliation

↓

Efficient Update
```

---

```text
Good Key

↓

Unique

↓

Stable

↓

Never Changes
```

---

```text
Large JSX

↓

Extract Component

↓

Reusable
```

---

```text
Empty List

↓

Fallback UI

↓

Better UX
```