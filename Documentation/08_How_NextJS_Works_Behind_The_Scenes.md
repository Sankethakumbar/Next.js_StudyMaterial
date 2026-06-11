# How Next.js Works Behind the Scenes

## Topics Covered

1. What Happens When You Run npm run dev?
2. Development Server
3. What is JSX?
4. How JSX Becomes HTML
5. What is Babel?
6. What is Webpack?
7. Entry and Output
8. Loaders
9. Plugins
10. Complete Flow: Code to Screen
11. Why Next.js Feels Fast
12. Quick Recap
13. Interview Questions

---

# What Happens When You Run npm run dev?

When you run:

```bash
npm run dev
```

Next.js starts a Development Server on your computer.

The Development Server:

* Reads project files
* Compiles code
* Watches file changes
* Serves pages to the browser

Example:

```text
npm run dev
       ↓
Development Server Starts
       ↓
localhost:3000
       ↓
Application Visible
```

---

# Development Server

A Development Server is a temporary server used while building applications.

Its responsibilities:

* Run the application locally
* Detect file changes
* Rebuild code automatically
* Update the browser

Without a development server, developers would need to manually rebuild and refresh the application after every change.

---

# What is JSX?

JSX stands for:

```text
JavaScript XML
```

JSX allows developers to write HTML-like syntax inside JavaScript.

Example:

```jsx
<h1>Hello React</h1>
```

Although it looks like HTML, browsers cannot understand JSX directly.

JSX must first be converted into JavaScript.

---

## Why JSX?

Without JSX:

```javascript
React.createElement(
  "h1",
  null,
  "Hello React"
);
```

With JSX:

```jsx
<h1>Hello React</h1>
```

JSX makes UI code:

* Easier to read
* Easier to write
* Easier to maintain

---

# How JSX Becomes HTML

Browsers understand:

* HTML
* CSS
* JavaScript

Browsers do NOT understand JSX.

Therefore JSX must be converted before execution.

Flow:

JSX → converted by _Babel_  → becomes _Javascript_ → creates _html_ on the screen.
---

# What is Babel?

Babel is a JavaScript Compiler.

Its job is to convert modern JavaScript and JSX into browser-friendly JavaScript.

Example:

JSX:

```jsx
<h1>Hello React</h1>
```

Babel converts it into:

```javascript
React.createElement(
  "h1",
  null,
  "Hello React"
);
```

---

## Why Babel is Needed?

Different browsers support JavaScript features differently.

Babel ensures code works consistently across browsers.

Responsibilities:

* Convert JSX
* Convert modern JavaScript
* Improve browser compatibility

---

# What is Webpack?

Webpack is a Module Bundler.

Modern applications contain many files:

* JavaScript
* CSS
* Images
* Fonts

Webpack combines and organizes these files into optimized bundles.
This makes your app load faster and work smoothly in the browser.

Think of Webpack as a packaging system that prepares your application for the browser.

---

# Entry and Output

Webpack starts from an Entry File.

Example:

```text
src/app/page.js
```

↓

Webpack follows imports and dependencies.

↓

Creates optimized bundles.

↓

Produces Output Files.

Flow:

```text
Entry File
      ↓
Process Dependencies
      ↓
Bundle Files
      ↓
Output
```

---

# What are Loaders?

Loaders tell Webpack how to process different file types.

Examples:

### CSS Loader

Processes CSS files.

```css
body {
  margin: 0;
}
```

---

### Image Loader

Processes images.

```text
logo.png
```

---

### Babel Loader

Processes JSX and JavaScript.

```jsx
<h1>Hello</h1>
```

↓

JavaScript

Without loaders, Webpack would not know how to handle these files.

---

# What are Plugins?

Plugins extend Webpack's functionality.

They perform additional tasks during the build process.

Examples:

* Optimize bundles
* Compress files
* Generate HTML files
* Improve performance

Think of plugins as extra tools that make the application faster and better optimized.

---

# Complete Flow: Code to Screen

When a developer writes code:

```jsx
export default function Home() {
  return <h1>Hello React!</h1>;
}
```

The following happens:

```text
Developer Writes JSX
           ↓
Babel
           ↓
Converts JSX to JavaScript
           ↓
Webpack
           ↓
Bundles Application Files
           ↓
Next.js Development Server
           ↓
Browser Receives Code
           ↓
React Creates DOM Elements
           ↓
HTML Appears on Screen
```

---

# Why Next.js Feels Fast

Next.js automates:

* Babel Configuration
* Webpack Configuration
* Development Server Setup
* Hot Reloading
* Optimization

Developers simply write code.

Next.js handles the complex tooling behind the scenes.

This improves:

* Development Speed
* Performance
* Developer Experience

---

# Visual Summary

```text
Developer Writes JSX
         ↓
Babel
         ↓
JavaScript
         ↓
Webpack
         ↓
Optimized Bundle
         ↓
Next.js Server
         ↓
Browser
         ↓
HTML Displayed
```

---

# Quick Recap

## JSX

HTML-like syntax inside JavaScript.

---

## Babel

Converts JSX and modern JavaScript into browser-friendly JavaScript.

---

## Webpack

Bundles project files.

---

## Loaders

Tell Webpack how to process different file types.

---

## Plugins

Add extra functionality during the build process.

---

## npm run dev

Starts the development server.

---

# Interview Questions

## What happens when npm run dev is executed?

It starts the Next.js development server, compiles the application, watches file changes, and serves the app locally.

---

## What is JSX?

JSX is a syntax extension that allows HTML-like code inside JavaScript.

---

## Why can't browsers understand JSX directly?

Because JSX is not standard JavaScript and must first be converted by Babel.

---

## What is Babel?

Babel is a JavaScript compiler that converts JSX and modern JavaScript into browser-compatible JavaScript.

---

## What is Webpack?

Webpack is a module bundler that combines application files into optimized bundles.

---

## What is the role of Entry and Output in Webpack?

Entry is the starting file, and Output is the final optimized bundle produced by Webpack.

---

## What are Loaders?

Loaders tell Webpack how to process different file types such as CSS, images, and JSX.

---

## What are Plugins?

Plugins extend Webpack functionality and perform tasks like optimization and compression.

---

## Complete the Flow:

```text
JSX
 ↓
________
 ↓
JavaScript
 ↓
HTML
```

Answer:

```text
Babel
```

---

## Complete the Flow:

```text
Developer
 ↓
JSX
 ↓
Babel
 ↓
________
 ↓
Browser
```

Answer:

```text
Webpack
```

---

## How does JSX become HTML?

```text
JSX
 ↓
Babel
 ↓
JavaScript
 ↓
React
 ↓
HTML
 ↓
Browser
```
