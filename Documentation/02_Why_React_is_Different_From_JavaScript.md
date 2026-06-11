# Why React is Different From Traditional JavaScript

## 1. Traditional JavaScript Approach

## 2. Problems with Traditional JavaScript

## 3. React Approach

## 4. Imperative vs Declarative Programming

## 5. What is DOM?

## 6. How JavaScript Updates DOM

## 7. How React Updates UI

## 8. React Rendering Flow (Preview)

## 9. Benefits of React's Approach

## 10. Interview Questions


## Traditional JavaScript Approach

In traditional JavaScript, developers directly manipulate the DOM.

Whenever data changes, the developer must manually:

1. Find the element.
2. Update the element.
3. Ensure the UI remains synchronized.

Example:

document.getElementById("title").innerText = "Hello Alex";

The developer controls every UI update manually.





## Problems with Traditional JavaScript

As applications grow larger, managing UI manually becomes difficult.

### 1. Repetitive DOM Manipulation

Developers constantly update elements manually.

### 2. Complex State Management

Tracking changing data becomes difficult.

### 3. Maintainability Issues

Code becomes harder to organize and update.

### 4. Debugging Complexity

Finding which code changed which element becomes challenging.

### 5. Performance Problems

Frequent DOM updates can slow down applications.



## React Approach

React follows a different strategy.

Instead of manually updating the DOM:

Developers describe what the UI should look like.

Whenever data changes:

React determines what needs updating and performs the updates automatically.

The developer focuses on data and business logic rather than DOM manipulation.


## Imperative Programming

Imperative programming focuses on HOW to achieve a result.

Example:

1. Create element
2. Set text
3. Append element

The developer specifies every step.

JavaScript DOM manipulation is primarily imperative.


## Declarative Programming

Declarative programming focuses on WHAT the final UI should look like.

Example:

<h1>Hello Alex</h1>

React determines how to update the page internally.

React uses a declarative approach.




JavaScript → HOW

React → WHAT



## What is DOM?

DOM stands for Document Object Model.

The browser converts HTML into a tree-like structure called the DOM.

JavaScript uses the DOM to access and modify webpage content.

Example:

Document
|
|-- html
    |
    |-- head
    |
    |-- body
         |
         |-- h1
         |
         |-- p

The DOM is a tree representation of an HTML document that allows JavaScript to access and modify webpage elements.


## How JavaScript Updates DOM

Example:

document.getElementById("title").innerText = "Hello";

Steps:

1. Find element.
2. Modify content.
3. Browser updates page.

This process is repeated whenever data changes.


## How React Updates UI

React does not update the DOM directly every time data changes.

Instead:

1. React creates a Virtual DOM.
2. React compares changes.
3. React updates only necessary parts.

This makes UI updates more efficient.




## React Rendering Flow

Data Changes

↓

Component Re-renders

↓

New Virtual DOM Created

↓

Diffing

↓

Reconciliation

↓
Real DOM Updated



Re-rendering:
React generates updated UI.

Virtual DOM:
Lightweight copy of the Real DOM.

Diffing:
Comparison of old and new Virtual DOM.

Reconciliation:
Process of updating the Real DOM efficiently.



## Benefits of React

### Better Performance

Fewer DOM updates.

### Cleaner Code

Less manual manipulation.

### Better Maintainability

Code remains organized.

### Reusability

UI can be divided into reusable components.

### Scalability

Applications can grow more easily.




## Interview Questions

1. Why is React different from JavaScript?

2. What is DOM?

3. What are the problems with direct DOM manipulation?

4. What is Declarative Programming?

5. What is Imperative Programming?

6. Why is React easier to maintain?

7. How does React update the UI?

8. What is Virtual DOM?

9. What is Re-rendering?

10. What is Reconciliation?