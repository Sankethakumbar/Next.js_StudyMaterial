# Fallback UI

## 📚 Topics Covered

- What is Fallback UI?
- Why do we need Fallback UI?
- Empty State
- Loading State
- Best Practices

---

# 📖 Definition

Fallback UI is a **backup UI** shown when the main content cannot be displayed.

Instead of showing a blank screen, React displays a meaningful message or placeholder.

---

# 🤔 Why Do We Need Fallback UI?

Without Fallback UI:

- Blank screens confuse users.
- Users may think the application is broken.

With Fallback UI:

- Improves User Experience (UX).
- Keeps users informed.
- Makes the application feel responsive.

---

# 🧠 Mind Map

```text
Component
    │
    ▼
Is Data Available?
    │
 ┌──┴──┐
 │     │
Yes    No
 │      │
 ▼      ▼
Show    Fallback UI
Data
```

---

# 📌 Types of Fallback UI

## 1️⃣ Empty State

### Definition

Shown when there is **no data** to display.

### Examples

- No Products Found
- No Messages
- No Notifications
- No Search Results
- Empty Cart

### Example

```jsx
return (
  <div>
    {hasProducts ? <ProductList /> : <p>No Products Found</p>}
  </div>
);
```

---

## 2️⃣ Loading State

### Definition

Shown while data is still loading.

Instead of showing a blank page, display a loading message or loader.

### Examples

- Loading...
- Fetching Data...
- Please Wait...

### Example

```jsx
return (
  <div>
    {isLoading ? <p>Loading...</p> : <ProductList />}
  </div>
);
```

---

# 🔄 Flow

```text
Component Loads
       │
       ▼
Is Loading?
       │
   ┌───┴────┐
   │        │
 Yes        No
   │         │
Loading...   ▼
        Is Data Available?
             │
        ┌────┴────┐
        │         │
      Yes         No
        │          │
        ▼          ▼
   Show Data   Empty State
```

---

# ✅ Advantages

- Improves User Experience (UX).
- Prevents blank screens.
- Makes applications feel responsive.
- Clearly communicates the current state to users.

---

# 🎯 Best Practices

- Always show a loading state while fetching data.
- Always provide an empty state when no data exists.
- Keep fallback messages simple and informative.
- Avoid leaving users with a blank screen.

---

# 📊 Empty State vs Loading State

| Empty State | Loading State |
|--------------|---------------|
| No data exists | Data is being fetched |
| Final state | Temporary state |
| Example: "No Products Found" | Example: "Loading..." |

---

# ⚠ Common Mistakes

### ❌ Showing a blank screen

Always display a meaningful message instead.

---

### ❌ Forgetting the loading state

Users may think the app has frozen.

---

### ❌ Confusing loading with empty state

Loading means the data **is coming**.

Empty means the data **has arrived, but there is nothing to show**.

---

# 📝 Quick Recap

- Fallback UI is a backup UI.
- Prevents blank screens.
- Two common types:
  - Empty State
  - Loading State
- Improves User Experience.

---

# 💼 Interview Questions

- What is Fallback UI?
- Why is Fallback UI important?
- What is an Empty State?
- What is a Loading State?
- Difference between Empty State and Loading State?
- Give some real-world examples of Fallback UI.