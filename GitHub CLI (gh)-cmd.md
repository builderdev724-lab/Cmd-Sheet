# GitHub CLI (gh) Command Cheat Sheet

> A complete guide to GitHub CLI (gh) commands for developers.

---

# Table of Contents

1. Installation
2. Authentication
3. Repository Management
4. Cloning Repositories
5. Branch Management
6. Pull Requests
7. Issues
8. Releases
9. GitHub Actions
10. Gists
11. SSH Keys
12. Useful Commands
13. Common Problems
14. Developer Workflow
15. Essential Commands
16. Best Practices

---

# 1. Installation

Ubuntu

```bash
sudo apt install gh
```

Verify Installation

```bash
gh --version
```

Show Help

```bash
gh help
```

---

# 2. Authentication

Login

```bash
gh auth login
```

Check Login Status

```bash
gh auth status
```

Logout

```bash
gh auth logout
```

Refresh Authentication

```bash
gh auth refresh
```

---

# 3. Repository Management

Create Repository

```bash
gh repo create
```

Clone Repository

```bash
gh repo clone owner/repository
```

Fork Repository

```bash
gh repo fork
```

View Repository

```bash
gh repo view
```

Open Repository in Browser

```bash
gh repo view --web
```

Delete Repository

```bash
gh repo delete owner/repository
```

Rename Repository

```bash
gh repo rename new-name
```

---

# 4. Cloning Repositories

Clone via SSH

```bash
gh repo clone owner/repository
```

Clone into Specific Folder

```bash
gh repo clone owner/repository my-folder
```

---

# 5. Branch Management

View Default Branch

```bash
gh repo view
```

Create Branch (Git)

```bash
git checkout -b feature/auth
```

Push Branch

```bash
git push origin feature/auth
```

---

# 6. Pull Requests

Create PR

```bash
gh pr create
```

List PRs

```bash
gh pr list
```

View PR

```bash
gh pr view
```

Checkout PR

```bash
gh pr checkout 24
```

Merge PR

```bash
gh pr merge
```

Close PR

```bash
gh pr close
```

Reopen PR

```bash
gh pr reopen
```

Open PR in Browser

```bash
gh pr view --web
```

---

# 7. Issues

Create Issue

```bash
gh issue create
```

List Issues

```bash
gh issue list
```

View Issue

```bash
gh issue view 10
```

Close Issue

```bash
gh issue close 10
```

Reopen Issue

```bash
gh issue reopen 10
```

Assign Issue

```bash
gh issue edit 10 --add-assignee @me
```

---

# 8. Releases

Create Release

```bash
gh release create v1.0.0
```

List Releases

```bash
gh release list
```

View Release

```bash
gh release view
```

Download Assets

```bash
gh release download
```

Delete Release

```bash
gh release delete v1.0.0
```

---

# 9. GitHub Actions

List Workflows

```bash
gh workflow list
```

Run Workflow

```bash
gh workflow run ci.yml
```

View Workflow Runs

```bash
gh run list
```

View Run Details

```bash
gh run view
```

Watch Workflow

```bash
gh run watch
```

Download Logs

```bash
gh run download
```

---

# 10. Gists

Create Gist

```bash
gh gist create file.txt
```

List Gists

```bash
gh gist list
```

View Gist

```bash
gh gist view
```

Edit Gist

```bash
gh gist edit
```

Delete Gist

```bash
gh gist delete
```

---

# 11. SSH Keys

Upload SSH Key

```bash
gh ssh-key add ~/.ssh/id_ed25519.pub
```

List SSH Keys

```bash
gh ssh-key list
```

---

# 12. Useful Commands

View Notifications

```bash
gh api notifications
```

Browse Repository

```bash
gh browse
```

View API Rate Limit

```bash
gh api rate_limit
```

Search Repositories

```bash
gh search repos nestjs
```

Search Code

```bash
gh search code "class UserService"
```

---

# 13. Common Problems

Not Logged In

```bash
gh auth login
```

Authentication Status

```bash
gh auth status
```

Update GitHub CLI

```bash
gh extension upgrade --all
```

---

# 14. Developer Workflow

Clone Repository

```bash
gh repo clone owner/project
```

Create Feature Branch

```bash
git checkout -b feature/login
```

Commit Changes

```bash
git commit -m "Add login feature"
```

Push Branch

```bash
git push origin feature/login
```

Create Pull Request

```bash
gh pr create
```

Watch CI

```bash
gh run watch
```

Merge PR

```bash
gh pr merge
```

---

# 15. Essential Commands

```bash
gh auth login
gh auth status

gh repo create
gh repo clone
gh repo view

gh pr create
gh pr list
gh pr view
gh pr checkout
gh pr merge

gh issue create
gh issue list
gh issue close

gh workflow list
gh workflow run

gh run list
gh run watch

gh release create
gh release list

gh gist create

gh browse
gh --version
```

---

# 16. Best Practices

- Authenticate using `gh auth login`.
- Use SSH authentication for Git operations when possible.
- Create pull requests from the terminal to streamline your workflow.
- Review workflow status before merging changes.
- Keep the GitHub CLI updated.
- Use `gh repo view --web` to quickly open repositories in your browser.
- Use `gh run watch` to monitor CI/CD pipelines in real time.