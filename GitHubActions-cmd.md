# GitHub Actions Command Cheat Sheet

> A complete guide to GitHub Actions workflows, CLI commands, and CI/CD automation.

---

# Table of Contents

1. What is GitHub Actions
2. Workflow Structure
3. Workflow Management
4. Running Workflows
5. Workflow Runs
6. Logs
7. Artifacts
8. Environment Variables
9. Secrets
10. Matrix Builds
11. Common Events
12. Debugging
13. Common Problems
14. Developer Workflow
15. Essential Commands
16. Best Practices

---

# 1. What is GitHub Actions

Workflow Location

```
.github/workflows/
```

Example

```
.github/workflows/ci.yml
```

---

# 2. Workflow Structure

Basic Workflow

```yaml
name: CI

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-node@v4
        with:
          node-version: 22

      - run: npm install
      - run: npm run build
```

Validate Workflow

```bash
yamllint .github/workflows/ci.yml
```

---

# 3. Workflow Management

List Workflows

```bash
gh workflow list
```

View Workflow

```bash
gh workflow view ci.yml
```

Enable Workflow

```bash
gh workflow enable ci.yml
```

Disable Workflow

```bash
gh workflow disable ci.yml
```

---

# 4. Running Workflows

Run Workflow

```bash
gh workflow run ci.yml
```

Run With Branch

```bash
gh workflow run ci.yml --ref develop
```

---

# 5. Workflow Runs

List Runs

```bash
gh run list
```

View Run

```bash
gh run view
```

Watch Run

```bash
gh run watch
```

Cancel Run

```bash
gh run cancel RUN_ID
```

Rerun

```bash
gh run rerun RUN_ID
```

Delete Run

```bash
gh run delete RUN_ID
```

---

# 6. Logs

View Logs

```bash
gh run view --log
```

Download Logs

```bash
gh run download
```

---

# 7. Artifacts

Download Artifact

```bash
gh run download
```

Upload Artifact

```yaml
- uses: actions/upload-artifact@v4
```

Download Artifact

```yaml
- uses: actions/download-artifact@v4
```

---

# 8. Environment Variables

Workflow Variable

```yaml
env:
  NODE_ENV: production
```

Job Variable

```yaml
jobs:
  build:
    env:
      PORT: 3000
```

Step Variable

```yaml
- run: echo $PORT
```

---

# 9. Secrets

Repository Secret

```
Settings → Secrets and variables
```

Access Secret

```yaml
${{ secrets.DATABASE_URL }}
```

List Secrets

```bash
gh secret list
```

Create Secret

```bash
gh secret set DATABASE_URL
```

Delete Secret

```bash
gh secret delete DATABASE_URL
```

---

# 10. Matrix Builds

```yaml
strategy:
  matrix:
    node-version: [20,22]
```

---

# 11. Common Events

Push

```yaml
on:
  push:
```

Pull Request

```yaml
on:
  pull_request:
```

Manual

```yaml
on:
  workflow_dispatch:
```

Schedule

```yaml
on:
  schedule:
    - cron: "0 0 * * *"
```

Release

```yaml
on:
  release:
```

---

# 12. Debugging

Workflow Logs

```bash
gh run view --log
```

List Runs

```bash
gh run list
```

Watch

```bash
gh run watch
```

---

# 13. Common Problems

Workflow Not Running

Check

```yaml
on:
```

Wrong Branch

```bash
gh workflow run ci.yml --ref main
```

View Errors

```bash
gh run view --log
```

---

# 14. Developer Workflow

Commit Code

```bash
git add .
git commit -m "Feature"
git push
```

Watch Pipeline

```bash
gh run watch
```

Inspect Logs

```bash
gh run view --log
```

Download Artifacts

```bash
gh run download
```

Merge PR

```bash
gh pr merge
```

---

# 15. Essential Commands

```bash
gh workflow list
gh workflow view
gh workflow run
gh workflow enable
gh workflow disable

gh run list
gh run watch
gh run view
gh run rerun
gh run cancel
gh run delete
gh run download

gh secret list
gh secret set
gh secret delete
```

---

# 16. Best Practices

- Keep workflows in `.github/workflows/`.
- Use reusable workflows for common tasks.
- Store credentials in GitHub Secrets, never in the repository.
- Pin GitHub Actions to stable versions (for example, `@v4`).
- Run tests, linting, and type checking before deployments.
- Use matrix builds to test multiple Node.js versions.
- Monitor workflow execution using `gh run watch`.
- Review workflow logs before rerunning failed jobs.