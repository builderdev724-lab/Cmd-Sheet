# WebStorm Command Cheat Sheet

> A complete guide to WebStorm commands, CLI options, and developer workflows.

---

# Table of Contents

1. Installation
2. CLI Launcher
3. Opening Projects
4. Windows & Sessions
5. Toolbox App
6. Plugins
7. Settings
8. Terminal
9. Debugging
10. Database Tools
11. HTTP Client
12. Git Integration
13. Remote Development
14. Cache Management
15. Useful Commands
16. Common Problems
17. Developer Workflow
18. Essential Commands
19. Best Practices

---

# 1. Installation

Ubuntu (JetBrains Toolbox Recommended)

Download JetBrains Toolbox and install WebStorm.

Check Version

```bash
webstorm --version
```

Show Help

```bash
webstorm --help
```

---

# 2. CLI Launcher

Create Launcher

```
Tools → Create Command-line Launcher
```

Default Command

```bash
webstorm
```

---

# 3. Opening Projects

Open Current Folder

```bash
webstorm .
```

Open Folder

```bash
webstorm ~/Projects/api
```

Open File

```bash
webstorm app.ts
```

Open Multiple Files

```bash
webstorm app.ts package.json
```

Open New Window

```bash
webstorm --new-window .
```

Reuse Existing Window

```bash
webstorm --reuse-window .
```

---

# 4. Windows & Sessions

Open Existing Project

```bash
webstorm /path/to/project
```

Recent Projects

```
File → Open Recent
```

---

# 5. Toolbox App

Update IDE

```
JetBrains Toolbox → Update
```

Manage Installations

```
JetBrains Toolbox
```

---

# 6. Plugins

Open Plugins

```
Settings → Plugins
```

Marketplace

```
JetBrains Marketplace
```

Install Plugin

```
Plugins → Marketplace → Install
```

Disable Plugin

```
Plugins → Disable
```

---

# 7. Settings

Open Settings

```
Ctrl + Alt + S
```

Search Settings

```
Ctrl + Alt + S
```

Export Settings

```
File → Manage IDE Settings
```

---

# 8. Terminal

Open Terminal

```
Alt + F12
```

New Terminal Tab

```
+
```

---

# 9. Debugging

Run

```
Shift + F10
```

Debug

```
Shift + F9
```

Stop

```
Ctrl + F2
```

Toggle Breakpoint

```
Ctrl + F8
```

---

# 10. Database Tools

Open Database Tool Window

```
View → Tool Windows → Database
```

Connect Database

```
+ → Data Source
```

---

# 11. HTTP Client

HTTP File

```
request.http
```

Run Request

```
Click ▶ beside request
```

Example

```http
GET https://example.com/api
```

---

# 12. Git Integration

Commit

```
Ctrl + K
```

Push

```
Ctrl + Shift + K
```

Pull

```
Git → Pull
```

Branches

```
Git → Branches
```

---

# 13. Remote Development

SSH Remote Development

```
JetBrains Gateway
```

Remote Interpreter

```
Settings → Python/Node Interpreter
```

---

# 14. Cache Management

Invalidate Caches

```
File → Invalidate Caches / Restart
```

Restart IDE

```
File → Restart IDE
```

---

# 15. Useful Commands

Open Log Directory

```
Help → Show Log
```

Search Everywhere

```
Shift Shift
```

Find Action

```
Ctrl + Shift + A
```

Recent Files

```
Ctrl + E
```

---

# 16. Common Problems

Invalidate Cache

```
File → Invalidate Caches / Restart
```

Restart IDE

```
File → Restart IDE
```

Repair Project Index

```
Invalidate Caches
```

---

# 17. Developer Workflow

Open Project

```bash
webstorm .
```

Run Development Server

```
Alt + F12

npm run dev
```

Debug

```
Shift + F9
```

Commit

```
Ctrl + K
```

Push

```
Ctrl + Shift + K
```

---

# 18. Essential Commands

```bash
webstorm .
webstorm project
webstorm app.ts
webstorm --help
webstorm --version
webstorm --new-window
webstorm --reuse-window
```

Keyboard

```
Shift Shift
Ctrl + Shift + A
Alt + F12
Ctrl + Alt + S
Shift + F9
Ctrl + K
Ctrl + Shift + K
Ctrl + E
```

---

# 19. Best Practices

- Install WebStorm through JetBrains Toolbox for easier updates.
- Enable autosave and code inspections.
- Use the built-in HTTP Client instead of external tools for API testing.
- Configure ESLint, Prettier, and TypeScript integration.
- Use the Database tool for PostgreSQL and MySQL management.
- Regularly invalidate caches if indexing issues occur.
- Learn Search Everywhere (`Shift Shift`) and Find Action (`Ctrl + Shift + A`) to navigate quickly.