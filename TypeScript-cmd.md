# TypeScript Command Cheat Sheet

> A complete guide to TypeScript compiler (tsc) commands and development tools.

---

# Table of Contents

1. Check Installation
2. Create a Project
3. Compile TypeScript
4. Watch Mode
5. tsconfig.json
6. Type Checking
7. Output Directory
8. Declaration Files
9. Source Maps
10. Build Mode
11. Project References
12. Useful Flags
13. Debugging
14. Common Problems
15. Developer Workflow
16. Essential Commands
17. Best Practices

---

# 1. Check Installation

Check TypeScript Version

```bash
tsc -v
```

or

```bash
npx tsc -v
```

---

# 2. Create a Project

Initialize TypeScript

```bash
npx tsc --init
```

Creates

```
tsconfig.json
```

---

# 3. Compile TypeScript

Compile Project

```bash
tsc
```

Compile One File

```bash
tsc app.ts
```

Specify Output

```bash
tsc app.ts --outDir dist
```

---

# 4. Watch Mode

Automatically Compile

```bash
tsc --watch
```

Short Form

```bash
tsc -w
```

---

# 5. tsconfig.json

Show Effective Config

```bash
tsc --showConfig
```

List Config

```bash
tsc --project tsconfig.json
```

---

# 6. Type Checking

Type Check Only

```bash
tsc --noEmit
```

Check Specific File

```bash
tsc app.ts --noEmit
```

---

# 7. Output Directory

Compile to dist

```bash
tsc --outDir dist
```

Specify Root

```bash
tsc --rootDir src
```

---

# 8. Declaration Files

Generate Declaration Files

```bash
tsc --declaration
```

Declaration Only

```bash
tsc --emitDeclarationOnly
```

---

# 9. Source Maps

Generate Source Maps

```bash
tsc --sourceMap
```

Inline Source Maps

```bash
tsc --inlineSourceMap
```

---

# 10. Build Mode

Build Project

```bash
tsc --build
```

Clean Build

```bash
tsc --build --clean
```

Force Rebuild

```bash
tsc --build --force
```

---

# 11. Project References

Build Referenced Projects

```bash
tsc --build
```

Verbose Build

```bash
tsc --build --verbose
```

---

# 12. Useful Flags

List Files

```bash
tsc --listFiles
```

List Emitted Files

```bash
tsc --listEmittedFiles
```

Diagnostics

```bash
tsc --diagnostics
```

Extended Diagnostics

```bash
tsc --extendedDiagnostics
```

Trace Module Resolution

```bash
tsc --traceResolution
```

Explain Included Files

```bash
tsc --explainFiles
```

---

# 13. Debugging

Show Compiler Help

```bash
tsc --help
```

Show All Options

```bash
tsc --all
```

Trace Resolution

```bash
tsc --traceResolution
```

---

# 14. Common Problems

Cannot Find Module

```bash
npm install
```

Type Check

```bash
tsc --noEmit
```

Delete Build

```bash
rm -rf dist
```

Compile Again

```bash
tsc
```

---

# 15. Developer Workflow

Initialize

```bash
npx tsc --init
```

Type Check

```bash
tsc --noEmit
```

Compile

```bash
tsc
```

Watch

```bash
tsc --watch
```

---

# 16. Essential Commands

```bash
tsc
tsc -v
tsc --watch
tsc --noEmit
tsc --init
tsc --build
tsc --project
tsc --showConfig
tsc --sourceMap
tsc --declaration
tsc --traceResolution
tsc --diagnostics
```

---

# 17. Best Practices

- Keep `strict` mode enabled.
- Use `--noEmit` in CI for type checking.
- Generate source maps for debugging.
- Prefer `npx tsc` if TypeScript is installed locally.
- Commit your `tsconfig.json`.
- Use project references for monorepos.