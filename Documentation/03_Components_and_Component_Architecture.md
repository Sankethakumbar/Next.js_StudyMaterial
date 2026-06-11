# Components and Component Architecture

## Topics Covered

1. Components - The Building Blocks
2. What Does a Component Do?
3. Components Are Written in JavaScript
4. Why Components?
5. Components Combine Logic and UI
6. Benefits of Keeping Logic and UI Together
7. The Component Tree
8. Root Component
9. Parent and Child Components
10. Component Thinking
11. Unidirectional Data Flow
12. Advantages of Components
13. Interview Questions

---

# Components - The Building Blocks

## What is a Component?

A Component is a small, reusable, and independent part of a webpage.

Each component controls a visible section of the User Interface (UI).

React applications are built by combining many components together.

### Examples

* Navbar
* Footer
* Button
* TodoList
* TodoItem
* Search Bar

Think of components like LEGO blocks.

Each block is independent and reusable.

Multiple blocks can be combined together to build something larger.

Similarly, React applications are built by combining multiple components.

---

## What Does a Component Do?

A component performs three main tasks:

1. Receives Data
2. Processes Data
3. Returns UI

### Flow

Data

↓

Component

↓

UI Displayed

Whatever a component returns is displayed on the screen.

If something does not return visible output, it generally should not be a component.

### Examples of Components

* Navbar
* Footer
* Product Card
* Button

### Examples that are NOT Components

* Helper Functions
* Variables
* Utility Functions

These support the application but do not directly render UI.

---

## Components Are Written in JavaScript

A React component is simply a JavaScript function that returns UI.

The code inside the component describes what should appear on the screen.

### Examples

A Button component may return a button element.

A Navbar component may return navigation links.

React converts these components into visible UI.

---

## Why Components?

Before Components:

Large applications often contained:

* Huge HTML files
* Repeated code
* Difficult maintenance
* Difficult debugging

As applications grew, managing everything in one place became difficult.

Components solve this problem by dividing the UI into smaller manageable pieces.

### Benefits

* Reusability
* Better Organization
* Easier Debugging
* Easier Maintenance
* Scalability

---

# Components Combine Logic and UI

## What Does This Mean?

One of React's biggest ideas is that a component contains both:

**UI + Logic**

Instead of separating structure and behavior, React keeps them together.

---

## Traditional Web Development

HTML

↓

Structure

CSS

↓

Styling

JavaScript

↓

Logic

The code is separated into different places.

---

## React Approach

Component

├── UI

├── Logic

├── State

└── Events

Everything related to a feature stays together.

This makes development easier and more organized.

---

## Example

Imagine a Login Button.

### UI

Login Button

### Logic

When Clicked

↓

Open Login Page

React keeps both inside the same component.

---

# Benefits of Keeping Logic and UI Together

## Reusability

The same component can be used multiple times.

### Example

ProductCard

↓

Card 1

Card 2

Card 3

Same component, different data.

---

## Easy to Understand and Debug

Since UI and logic are together:

* Easier to locate bugs
* Easier to modify code
* Easier to understand functionality

---

## Reduced Complexity

Developers do not need to search across multiple files.

Everything stays in one place.

---

## Faster Development

Developers can work on individual components independently.

This increases productivity and development speed.

---

# The Component Tree

## What is a Component Tree?

React applications are made up of components arranged in a tree-like structure.

This structure is called the Component Tree.

At the top of the tree is the Root Component.

All other components exist inside it.

---

## Example Component Tree

App

├── Navbar

├── TodoList

│ ├── TodoItem

│ ├── TodoItem

│ └── TodoItem

└── Footer

Each component can contain other components.

This process is called Nesting.

---

# Root Component

## What is a Root Component?

Every React application starts from a Root Component.

Usually:

App

The Root Component acts as the entry point of the application.

Every other component is rendered inside it.

Without the Root Component, the application cannot be displayed.

---

# Parent and Child Components

## Parent Component

A component that renders or contains other components.

### Example

TodoList

contains:

* TodoItem
* TodoItem
* TodoItem

Therefore:

TodoList = Parent Component

---

## Child Component

A component rendered inside another component.

### Example

TodoItem

is a Child Component of:

TodoList

---

## Relationship

App

↓

TodoList

↓

TodoItem

Parent → Child

---

# Component Thinking

## What is Component Thinking?

Component Thinking is the process of breaking a large UI into smaller reusable components before development.

Instead of asking:

"How do I build this page?"

React developers ask:

"What components make up this page?"

---

## Example

Amazon Product Page

React developers see:

App

├── Navbar

├── SearchBar

├── ProductImage

├── ProductInfo

├── Reviews

└── Footer

Each section becomes an individual component.

---

## Why Component Thinking?

### Better Reusability

Components can be reused throughout the application.

### Better Maintainability

Changes affect only a small section of the application.

### Better Scalability

Applications can grow without becoming difficult to manage.

### Better Team Collaboration

Different developers can work on different components simultaneously.

---

# Unidirectional Data Flow

## What is Unidirectional Data Flow?

React follows One-Way Data Flow.

Data moves from:

Parent

↓

Child

This is called Unidirectional Data Flow.

---

## Example

App

↓

TodoList

↓

TodoItem

Parents pass information to children.

Children use that information to determine what should be displayed.

---

## Benefits

* Predictable Behavior
* Easier Debugging
* Better Maintainability
* Easier State Management

---

# Advantages of Components

## Reusability

Components can be reused throughout the application.

## Better Code Organization

Applications are divided into smaller manageable pieces.

## Easier Maintenance

Changes can be made without affecting unrelated parts.

## Easier Testing

Components can be tested individually.

## Better Scalability

Applications can grow without becoming difficult to manage.

## Team Collaboration

Different developers can work on different components simultaneously.

---




# Interview Questions

## What is a Component?

A reusable and independent building block of a React application.

## Why are Components important?

Components improve reusability, maintainability, scalability, and code organization.

## What is a Component Tree?

A hierarchical structure showing how React components are related.

## What is a Root Component?

The top-most component in a React application, usually App.

## What is a Parent Component?

A component that contains or renders other components.

## What is a Child Component?

A component rendered inside another component.

## What is Component Thinking?

Breaking a large UI into smaller reusable components before development.

## What is Unidirectional Data Flow?

A pattern where data flows from Parent Components to Child Components.

## Why does React combine UI and Logic?

To keep related code together and make applications easier to understand and maintain.

## What are the advantages of Components?

* Reusability
* Better Organization
* Easier Maintenance
* Easier Testing
* Scalability
* Team Collaboration
