# Node.js Command Cheat Sheet

> A complete guide to Node.js CLI commands for developers.

---

# Table of Contents

1. Check Installation
2. Running JavaScript
3. REPL
4. Environment Variables
5. Debugging
6. Profiling
7. Memory Management
8. Module Resolution
9. Watch Mode
10. Inspector
11. Experimental Features
12. Useful Flags
13. Common Problems
14. Developer Workflow
15. Essential Commands
16. Best Practices

---

# 1. Check Installation

Check Node Version

```bash
node -v
```

Example

```text
v22.18.0
```

---

Detailed Version Information

```bash
node -p process.versions
```

---

Platform Information

```bash
node -p process.platform
```

---

Architecture

```bash
node -p process.arch
```

---

# 2. Running JavaScript

Run File

```bash
node app.js
```

Run TypeScript (using tsx)

```bash
npx tsx src/index.ts
```

Evaluate Expression

```bash
node -e "console.log('Hello World')"
```

Print Result

```bash
node -p "2 + 5"
```

---

# 3. Node REPL

Start REPL

```bash
node
```

Exit

```text
.exit
```

Clear Screen

```text
.clear
```

---

# 4. Environment Variables

Set Variable (Linux/macOS)

```bash
NODE_ENV=development node app.js
```

View Environment

```bash
node -p process.env
```

Specific Variable

```bash
node -p process.env.NODE_ENV
```

---

# 5. Debugging

Start Inspector

```bash
node --inspect app.js
```

Break Before Execution

```bash
node --inspect-brk app.js
```

Attach Chrome DevTools

```
chrome://inspect
```

---

# 6. Profiling

CPU Profile

```bash
node --prof app.js
```

Heap Snapshot

```bash
node --heap-prof app.js
```

Trace Events

```bash
node --trace-events-enabled app.js
```

---

# 7. Memory Management

Increase Memory Limit

```bash
node --max-old-space-size=4096 app.js
```

Garbage Collection Logs

```bash
node --trace-gc app.js
```

---

# 8. Module Resolution

Find Module

```bash
node -p "require.resolve('express')"
```

Print Module Paths

```bash
node -p "module.paths"
```

---

# 9. Watch Mode

Run in Watch Mode

```bash
node --watch app.js
```

Watch Specific Path

```bash
node --watch-path=src app.js
```

---

# 10. Inspector

Open Inspector

```bash
node inspect app.js
```

---

# 11. Experimental Features

Enable Source Maps

```bash
node --enable-source-maps app.js
```

View Help

```bash
node --help
```

---

# 12. Useful Flags

Check Syntax

```bash
node --check app.js
```

Trace Warnings

```bash
node --trace-warnings app.js
```

Show Pending Deprecations

```bash
node --pending-deprecation app.js
```

Show Process Report

```bash
node --report-on-fatalerror app.js
```

---

# 13. Common Problems

Out of Memory

```bash
node --max-old-space-size=4096 app.js
```

Module Not Found

```bash
npm install
```

Syntax Check

```bash
node --check app.js
```

---

# 14. Developer Workflow

Check Version

```bash
node -v
```

Install Dependencies

```bash
npm install
```

Run Project

```bash
node app.js
```

Debug

```bash
node --inspect app.js
```

Watch Mode

```bash
node --watch app.js
```

---

# 15. Essential Commands

```bash
node -v
node app.js
node
node --watch
node --inspect
node --inspect-brk
node --check
node --help
node -e
node -p
node --prof
node --heap-prof
node --trace-gc
node --enable-source-maps
```

---

# 16. Best Practices

- Use the latest LTS version of Node.js for production.
- Prefer `node --watch` during development when appropriate.
- Enable source maps for better stack traces.
- Increase memory only when necessary.
- Use the inspector for debugging instead of `console.log` where possible.
- Use `tsx` or your framework's tooling to run TypeScript directly during development.