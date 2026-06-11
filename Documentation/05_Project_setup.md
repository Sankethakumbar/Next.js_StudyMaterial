# Creating and Running a Next.js Project

## Topics Covered

1. Before You Begin
2. Creating a Next.js Project
3. Understanding the create-next-app Command
4. Setup Questions and Configuration
5. Installation Process
6. Navigating to the Project Folder
7. What Happens Behind the Scenes?
8. Running the Project
9. Understanding npm run dev
10. What is localhost?
11. What is Port 3000?
12. Opening the Application
13. Stopping the Development Server
14. Common Errors and Solutions
15. Quick Recap
16. Interview Questions

---

# Before You Begin

Before creating a Next.js project, ensure:

* Node.js is installed
* npm is installed
* Internet connection is available
* Terminal or Command Prompt is open

The terminal will be used to create and manage the project.

---

# Creating a Next.js Project

To create a new project, run:

```bash
npx create-next-app@latest
```

After pressing Enter, setup begins.

You may see:

```text
Need to install the following packages:
create-next-app

Ok to proceed? (y)
```

Type:

```text
y
```

and press Enter.

---

# Understanding the create-next-app Command

```bash
npx create-next-app@latest
```

## npx

Allows packages to run directly without permanently installing them.

---

## create-next-app

Official package provided by Next.js.

It automatically creates and configures a new Next.js project.

---

## @latest

Uses the latest available version.

This ensures the project starts with the newest features and improvements.

---

# Setup Questions and Configuration

During project creation, Next.js asks several configuration questions.

The following table explains each option and the recommended choice.

| Setup Question                                                 | Purpose                                           | Recommended Choice |
| -------------------------------------------------------------- | ------------------------------------------------- | ------------------ |
| Would you like to use TypeScript?                              | Adds static typing to JavaScript.                 | No                 |
| Which linter would you like to use?                            | Checks code quality and coding mistakes.          | ESLint             |
| Would you like to use React Compiler?                          | Automatically optimizes React code.               | No                 |
| Would you like to use Tailwind CSS?                            | Utility-first CSS framework.                      | No                 |
| Would you like your code inside a src/ directory?              | Organizes files inside a dedicated source folder. | No                 |
| Would you like to use App Router?                              | Modern routing system used by Next.js.            | Yes                |
| Would you like to use Turbopack?                               | Fast development bundler.                         | Yes                |
| Would you like to customize the import alias (@/* by default)? | Creates custom import shortcuts.                  | No                 |

---

## Recommended Setup

```text
TypeScript      → No
ESLint          → Yes
React Compiler  → No
Tailwind CSS    → No
src Directory   → No
App Router      → Yes
Turbopack       → Yes
Import Alias    → No
```

This setup keeps the project simple while using modern Next.js features.

---

# Installation Process

After answering all questions:

Next.js automatically:

* Creates the project structure
* Installs React
* Installs Next.js
* Downloads dependencies
* Creates configuration files

This may take a few minutes depending on internet speed.

---

# Navigating to the Project Folder

Move into the project folder:

```bash
cd my-app
```

## What does cd mean?

```text
cd = Change Directory
```

It changes the current folder inside the terminal.

---

# What Happens Behind the Scenes?

When you run:

```bash
npx create-next-app@latest
```

the following steps occur automatically:

### Step 1

Downloads create-next-app.

### Step 2

Creates the project structure.

### Step 3

Installs React.

### Step 4

Installs Next.js.

### Step 5

Downloads dependencies.

### Step 6

Creates package.json.

### Step 7

Creates node_modules.

### Step 8

Adds configuration files.

Without Next.js, developers would need to perform all these tasks manually.

---

# Running the Project

Move inside the project folder:

```bash
cd my-app
```

Start the development server:

```bash
npm run dev
```

---

# Understanding npm run dev

This command starts the development server.

It:

* Compiles the application
* Starts the Next.js server
* Watches file changes
* Enables Hot Reloading

Flow:

```text
Project
   ↓
npm run dev
   ↓
Development Server Starts
   ↓
localhost:3000
   ↓
Application Visible in Browser
```

---

# What Happens When You Run It?

After running:

```bash
npm run dev
```

You should see:

```text
Local: http://localhost:3000
```

This means the application is running successfully.

---

# What is localhost?

localhost refers to your own computer.

When the development server starts, your computer temporarily acts as a web server.

The application is accessible only on your machine.

---

# What is Port 3000?

A port is a communication channel used by applications.

Next.js uses:

```text
3000
```

by default.

Example:

```text
http://localhost:3000
```

Means:

* localhost → Your Computer
* 3000 → Application Port

---

# Opening the Application

Open any browser:

* Chrome
* Edge
* Firefox

Visit:

```text
http://localhost:3000
```

Your Next.js application should appear.

Congratulations! Your first React application is now running.

---

# Stopping the Development Server

To stop the server:

```text
Ctrl + C
```

inside the terminal.

To restart:

```bash
npm run dev
```

---

# Common Errors and Solutions

## Port Already in Use

Error:

```text
Port 3000 is already in use
```

This means another application is already using Port 3000.

---

## Find Which Process Uses the Port

### Mac/Linux

```bash
lsof -i :3000
```

### Windows

```bash
netstat -ano | findstr :3000
```

This displays the Process ID (PID).

---

## Kill the Process

### Mac/Linux

```bash
kill -9 PID
```

Example:

```bash
kill -9 12345
```

---

### Windows

```bash
taskkill /PID 12345 /F
```

---

## Run on Another Port

```bash
npm run dev -- -p 3001
```

Then open:

```text
http://localhost:3001
```

---

## npm run dev Not Working

Check:

* Node.js installed correctly
* npm installed correctly
* Dependencies installed using npm install
* You are inside the project folder

---

# Quick Recap

```text
npx create-next-app@latest
          ↓
Creates Next.js Project
          ↓
cd my-app
          ↓
Move into Project Folder
          ↓
npm run dev
          ↓
Start Development Server
          ↓
localhost:3000
          ↓
Application Visible
          ↓
Ctrl + C
          ↓
Stop Server
```

---

# Interview Questions

## What command is used to create a Next.js project?

```bash
npx create-next-app@latest
```

---

## What does npx do?

Runs packages directly without permanently installing them.

---

## What does create-next-app do?

Creates and configures a new Next.js project.

---

## What does @latest mean?

Uses the latest available version.

---

## What command is used to start a Next.js project?

```bash
npm run dev
```

---

## What is localhost?

localhost refers to your own computer acting as a local server.

---

## What is Port 3000?

The default port used by the Next.js development server.

---

## How do you stop the development server?

```text
Ctrl + C
```

---

## How do you run the application on another port?

```bash
npm run dev -- -p 3001
```

---

## What happens when npm run dev is executed?

It starts the development server, compiles the application, watches file changes, and enables hot reloading.
