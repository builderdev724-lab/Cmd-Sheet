# Visual Studio Code Command Cheat Sheet

> A complete guide to Visual Studio Code (VS Code) commands, CLI options, and developer workflows.

---

# Table of Contents

1. Installation
2. Launching VS Code
3. Opening Files & Folders
4. Workspaces
5. Extensions
6. Profiles
7. Settings
8. Terminal
9. Debugging
10. Tasks
11. Git Integration
12. Remote Development
13. Dev Containers
14. Useful CLI Options
15. Troubleshooting
16. Developer Workflow
17. Essential Commands
18. Best Practices

---

# 1. Installation

Ubuntu (Snap)

```bash
sudo snap install code --classic
```

Ubuntu (APT)

```bash
sudo apt install code
```

Check Version

```bash
code --version
```

Show Help

```bash
code --help
```

---

# 2. Launching VS Code

Open Current Directory

```bash
code .
```

Open Specific Folder

```bash
code my-project
```

Open File

```bash
code app.ts
```

Open Multiple Files

```bash
code app.ts package.json
```

Open New Window

```bash
code --new-window
```

Reuse Existing Window

```bash
code --reuse-window
```

---

# 3. Opening Files & Folders

Go to Specific Line

```bash
code -g app.ts:120
```

Open Folder

```bash
code ~/Projects/api
```

Open Multiple Folders

```bash
code backend frontend
```

---

# 4. Workspaces

Open Workspace

```bash
code project.code-workspace
```

Create Workspace

```
File → Save Workspace As...
```

---

# 5. Extensions

Install Extension

```bash
code --install-extension esbenp.prettier-vscode
```

Install Specific Version

```bash
code --install-extension ms-python.python@2025.10.0
```

List Extensions

```bash
code --list-extensions
```

Show Versions

```bash
code --list-extensions --show-versions
```

Uninstall Extension

```bash
code --uninstall-extension esbenp.prettier-vscode
```

Disable Extension

```bash
code --disable-extension ms-vscode.vscode-typescript-next
```

---

# 6. Profiles

List Profiles

```bash
code --list-profiles
```

Use Profile

```bash
code --profile "Web Development"
```

---

# 7. Settings

Open Settings JSON

```text
Ctrl + Shift + P
Preferences: Open User Settings (JSON)
```

Open Settings UI

```text
Ctrl + ,
```

---

# 8. Terminal

Open Integrated Terminal

```text
Ctrl + `
```

New Terminal

```text
Ctrl + Shift + `
```

Split Terminal

```text
Ctrl + Shift + 5
```

---

# 9. Debugging

Start Debugging

```text
F5
```

Stop

```text
Shift + F5
```

Step Over

```text
F10
```

Step Into

```text
F11
```

Toggle Breakpoint

```text
F9
```

---

# 10. Tasks

Run Task

```text
Ctrl + Shift + P

Tasks: Run Task
```

Configure Task

```
.vscode/tasks.json
```

---

# 11. Git Integration

Open Source Control

```text
Ctrl + Shift + G
```

View Diff

```bash
code --diff old.ts new.ts
```

Merge Editor

```bash
code --merge file1 file2 base result
```

---

# 12. Remote Development

Install Remote SSH Extension

```bash
code --install-extension ms-vscode-remote.remote-ssh
```

Connect

```
Remote Explorer → SSH Targets
```

---

# 13. Dev Containers

Install Dev Containers

```bash
code --install-extension ms-vscode-remote.remote-containers
```

Configuration

```
.devcontainer/
```

Reopen in Container

```
Ctrl + Shift + P

Dev Containers: Reopen in Container
```

---

# 14. Useful CLI Options

Wait Until Closed

```bash
code --wait file.txt
```

Disable Extensions

```bash
code --disable-extensions
```

Verbose Logging

```bash
code --verbose
```

Open Logs

```bash
code --log trace
```

Inspect Extensions

```bash
code --status
```

---

# 15. Troubleshooting

Reset Extensions

```bash
code --disable-extensions
```

Check Version

```bash
code --version
```

Verbose Mode

```bash
code --verbose
```

Show Running Processes

```bash
code --status
```

---

# 16. Developer Workflow

Open Project

```bash
code .
```

Install Recommended Extensions

```bash
code --install-extension dbaeumer.vscode-eslint
code --install-extension esbenp.prettier-vscode
```

Start Debugger

```text
F5
```

Open Terminal

```text
Ctrl + `
```

Commit Changes

```text
Ctrl + Shift + G
```

---

# 17. Essential Commands

```bash
code .
code app.ts
code -g
code --version
code --help
code --diff
code --merge
code --wait
code --list-extensions
code --install-extension
code --uninstall-extension
code --disable-extensions
code --status
code --verbose
```

---

# 18. Best Practices

- Use workspaces for multi-project repositories.
- Sync settings and extensions across devices.
- Install only the extensions you actively use.
- Configure formatters and linters for consistent code style.
- Use Dev Containers or Remote SSH for remote development.
- Keep extensions updated.
- Learn keyboard shortcuts to improve productivity.