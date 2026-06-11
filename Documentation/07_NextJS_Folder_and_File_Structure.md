# Next.js Folder and File Structure (App Router)

## Topics Covered

1. Overview of Project Structure
2. Understanding the src Folder
3. Understanding the app Folder
4. Understanding page.js
5. Understanding layout.js
6. Understanding the public Folder
7. Understanding the styles Folder
8. Understanding package.json
9. Understanding node_modules
10. Understanding next.config.js
11. Where Should You Write Your Code?
12. Quick Recap
13. Interview Questions

---

# Overview of Project Structure

A typical Next.js project looks like:

```text
my-app/
│
├── src/
│   └── app/
│       ├── page.js
│       └── layout.js
│
├── public/
│
├── styles/
│
├── package.json
│
├── node_modules/
│
└── next.config.js
```

Each folder and file has a specific responsibility.

Understanding this structure helps developers know where different types of code belong.

---

# Understanding the src Folder

The word src stands for:

```text
Source
```

The src folder contains the main source code of the application.

Examples:

* Components
* Pages
* Business Logic
* Hooks
* Utilities

Keeping code inside src helps separate application code from configuration files.

Benefits:

* Cleaner structure
* Better organization
* Easier maintenance

---

# Understanding the app Folder

The app folder is the most important folder in modern Next.js applications.

Location:

```text
src/app/
```

It contains:

* Pages
* Layouts
* Routes
* Route-specific files

Next.js uses this folder to create application routes automatically.

Example:

```text
app/
│
├── page.js
│
└── about/
    └── page.js
```

Routes:

```text
/
```

and

```text
/about
```

---

# Understanding page.js

The file:

```text
page.js
```

defines the UI of a route.

Example:

```text
app/page.js
```

represents:

```text
/
```

(Home Page)

---

Example:

```text
app/about/page.js
```

represents:

```text
/about
```

(About Page)

---

## Why page.js is Important?

page.js:

* Defines route content
* Returns UI
* Is automatically detected by Next.js
* Creates pages without manual routing

Without page.js, the route cannot be rendered.

---

# Understanding layout.js

layout.js defines UI that should appear on multiple pages.

Examples:

* Navbar
* Sidebar
* Footer
* Header

Instead of repeating these components on every page, layout.js allows them to be shared.

---

## Example

```text
layout.js
│
├── Navbar
├── Main Content
└── Footer
```

Whenever users navigate between pages:

Navbar and Footer remain visible.

Only page content changes.

---

## Why Use layout.js?

Benefits:

* Avoids duplicate code
* Consistent UI
* Easier maintenance

---

# Understanding the public Folder

The public folder stores static files.

Examples:

* Images
* Icons
* PDFs
* Videos

Example:

```text
public/
│
└── logo.png
```

Can be accessed as:

```text
/logo.png
```

inside the application.

---

## Why Use public?

Files inside public:

* Do not require importing
* Can be accessed directly
* Load efficiently

---

# Understanding the styles Folder

The styles folder contains CSS files.

Examples:

```text
styles/
│
├── globals.css
│
└── home.css
```

Purpose:

* Control appearance
* Add colors
* Define layouts
* Improve UI design

---

## globals.css

Usually contains styles applied across the entire application.

Example:

```css
body {
  margin: 0;
  font-family: Arial;
}
```

These styles affect all pages.

---

# Understanding package.json

package.json contains project information.

Examples:

* Project Name
* Dependencies
* Scripts
* Version Information

Example:

```json
{
  "name": "my-app",
  "dependencies": {
    "react": "...",
    "next": "..."
  }
}
```

It acts as the project's configuration file.

---

# Understanding node_modules

node_modules stores the actual code for installed packages.

Examples:

* React
* Next.js
* ESLint

The folder is generated automatically.

Developers usually never edit files inside node_modules.

---

## Why is node_modules Large?

Each package depends on other packages.

This creates thousands of files.

As a result:

```text
node_modules
```

can become very large.

---

# Understanding next.config.js

next.config.js is a configuration file for Next.js.

It controls advanced settings such as:

* Image optimization
* Redirects
* Environment settings
* Build configuration

Example:

```javascript
const nextConfig = {};

module.exports = nextConfig;
```

For beginners, this file usually requires no modification.

---

# Where Should You Write Your Code?

## Pages

Inside:

```text
src/app/
```

---

## Components

Usually inside:

```text
src/components/
```

(We will create this later.)

---

## Images

Inside:

```text
public/
```

---

## CSS

Inside:

```text
styles/
```

or alongside components.

---

## Configuration

Inside:

```text
next.config.js
```

---

# Visual Summary

```text
src/
│
├── app/
│   ├── page.js
│   └── layout.js
│
├── components/
│
└── styles/

public/
│
├── images
├── icons
└── assets

package.json

node_modules

next.config.js
```

---

# Quick Recap

```text
src/
    ↓
Main Application Code

app/
    ↓
Pages and Routes

page.js
    ↓
Route UI

layout.js
    ↓
Shared Layout

public/
    ↓
Static Assets

styles/
    ↓
CSS Files

package.json
    ↓
Project Configuration

node_modules
    ↓
Installed Packages

next.config.js
    ↓
Next.js Settings
```

---

# Interview Questions

## What is the purpose of the src folder?

It stores the main source code of the application.

---

## What is the app folder?

The app folder contains routes, pages, and layouts used by Next.js App Router.

---

## What is page.js?

page.js defines the UI for a route.

---

## What is layout.js?

layout.js defines shared UI that appears across multiple pages.

---

## What is the purpose of the public folder?

It stores static files such as images, icons, and PDFs.

---

## What is globals.css?

A CSS file that applies styles globally across the application.

---

## What is package.json?

A configuration file that stores project information, scripts, and dependencies.

---

## What is node_modules?

A folder containing the actual installed code of all dependencies.

---

## Why should node_modules not be uploaded to GitHub?

Because it is large and can be recreated using npm install.

---

## What is next.config.js?

A configuration file used to customize Next.js behavior.

---

## Where should React and Next.js code be written?

Inside the src/app folder and related component folders.

---

## What is App Router?

The modern routing system used by Next.js that automatically creates routes using folders and page.js files.
