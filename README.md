# Git Cheat Sheet

> A complete guide to Git commands, when to use them, and examples.

---

# Table of Contents

1. Initial Setup
2. Repository Management
3. Branching
4. Working with Changes
5. Commits
6. Remote Repositories
7. Synchronizing Changes
8. Merge & Rebase
9. Undoing Changes
10. Stashing
11. Tags
12. Logs & History
13. Inspection
14. Cleaning
15. Useful Shortcuts
16. Team Workflow
17. Common Problems & Fixes

---

# 1. Initial Setup

## Check Git Version

```bash
git --version
```

Use when:
- Checking if Git is installed.

---

## Configure Username

```bash
git config --global user.name "Your Name"
```

Use once after installing Git.

---

## Configure Email

```bash
git config --global user.email "you@example.com"
```

Use once.

---

## View Configuration

```bash
git config --list
```

Shows all Git settings.

---

# 2. Repository Management

## Initialize Repository

```bash
git init
```

Creates a new Git repository.

Use when:
- Starting a new project.

---

## Clone Repository

```bash
git clone <repository-url>
```

Example

```bash
git clone https://github.com/company/project.git
```

Use when:
- Downloading an existing repository.

---

# 3. Branching

## Show Local Branches

```bash
git branch
```

Shows only local branches.

---

## Show Remote Branches

```bash
git branch -r
```

Shows branches on GitHub/GitLab.

---

## Show All Branches

```bash
git branch -a
```

Shows local and remote branches.

---

## Create Branch

```bash
git branch feature/login
```

Creates a branch.

Does NOT switch to it.

---

## Switch Branch

```bash
git switch feature/login
```

or

```bash
git checkout feature/login
```

---

## Create and Switch

```bash
git switch -c feature/login
```

Old syntax

```bash
git checkout -b feature/login
```

---

## Delete Branch

```bash
git branch -d feature/login
```

Deletes merged branch.

Force delete

```bash
git branch -D feature/login
```

---

## Rename Branch

```bash
git branch -m old-name new-name
```

---

# 4. Working with Changes

## Check Status

```bash
git status
```

Most frequently used command.

Shows:

- Modified files
- Staged files
- Untracked files
- Current branch

---

## Add One File

```bash
git add app.js
```

---

## Add Multiple Files

```bash
git add file1 file2
```

---

## Add Everything

```bash
git add .
```

Adds all changed files.

---

## Interactive Add

```bash
git add -p
```

Allows adding changes chunk by chunk.

---

# 5. Commits

## Commit

```bash
git commit -m "Add login page"
```

Creates a commit.

---

## Commit All Tracked Files

```bash
git commit -am "Fix bug"
```

Does NOT include new files.

---

## Amend Last Commit

```bash
git commit --amend
```

Use when:
- Forgot a file
- Fix commit message

---

# 6. Remote Repositories

## View Remote

```bash
git remote -v
```

---

## Add Remote

```bash
git remote add origin <url>
```

---

## Change Remote URL

```bash
git remote set-url origin <new-url>
```

---

## Remove Remote

```bash
git remote remove origin
```

---

# 7. Synchronizing Changes

## Fetch

```bash
git fetch
```

Downloads changes.

Does NOT merge.

---

## Fetch Everything

```bash
git fetch --all
```

Downloads every remote.

---

## Remove Deleted Branches

```bash
git fetch --prune
```

Removes deleted remote references.

---

## Pull

```bash
git pull
```

Equivalent to

```bash
git fetch
git merge
```

---

## Pull with Rebase

```bash
git pull --rebase
```

Keeps history cleaner.

---

## Push

```bash
git push
```

Uploads commits.

---

## Push First Time

```bash
git push -u origin feature/login
```

Sets upstream.

Later simply use

```bash
git push
```

---

# 8. Merge & Rebase

## Merge Branch

```bash
git merge feature/login
```

---

## Rebase

```bash
git rebase main
```

Moves commits on top of another branch.

---

## Abort Merge

```bash
git merge --abort
```

---

## Abort Rebase

```bash
git rebase --abort
```

---

# 9. Undoing Changes

## Restore File

```bash
git restore file.txt
```

Discard local changes.

---

## Unstage File

```bash
git restore --staged file.txt
```

Removes from staging.

---

## Reset Last Commit

Keep changes

```bash
git reset --soft HEAD~1
```

---

Keep files

```bash
git reset HEAD~1
```

---

Delete everything

```bash
git reset --hard HEAD~1
```

Dangerous.

---

# 10. Stashing

## Save Work

```bash
git stash
```

---

## List

```bash
git stash list
```

---

## Restore

```bash
git stash pop
```

---

## Apply Without Removing

```bash
git stash apply
```

---

## Delete

```bash
git stash drop
```

---

## Delete All

```bash
git stash clear
```

---

# 11. Tags

Create tag

```bash
git tag v1.0
```

---

Push tag

```bash
git push origin v1.0
```

---

List tags

```bash
git tag
```

---

# 12. Logs & History

Simple log

```bash
git log
```

---

One line

```bash
git log --oneline
```

---

Graph

```bash
git log --graph --oneline --all
```

---

File history

```bash
git log filename
```

---

# 13. Inspection

Show differences

```bash
git diff
```

---

Staged differences

```bash
git diff --staged
```

---

Compare commits

```bash
git diff commit1 commit2
```

---

Show commit

```bash
git show
```

---

# 14. Cleaning

Preview

```bash
git clean -n
```

---

Delete untracked files

```bash
git clean -f
```

---

Delete folders too

```bash
git clean -fd
```

---

# 15. Useful Shortcuts

Current branch

```bash
git branch --show-current
```

---

Who changed what

```bash
git blame file.js
```

---

Search commits

```bash
git log --grep="login"
```

---

Find commit

```bash
git rev-parse HEAD
```

---

# 16. Team Workflow

## Starting Work

```bash
git pull
git switch develop
git pull
git switch -c feature/payment
```

---

## During Development

```bash
git status
git add .
git commit -m "Implement payment page"
```

---

## Push Branch

```bash
git push -u origin feature/payment
```

---

## Before Creating PR

```bash
git switch develop
git pull
git switch feature/payment
git merge develop
```

or

```bash
git rebase develop
```

---

## After PR Merged

```bash
git switch develop
git pull

git branch -d feature/payment

git fetch --prune
```

---

# 17. Common Problems & Fixes

## Friend created a branch but I can't see it

```bash
git fetch --all
git branch -r
git switch branch-name
```

---

## Deleted branch still appears

```bash
git fetch --prune
```

---

## Forgot to add a file

```bash
git add file
git commit --amend
```

---

## Wrong commit message

```bash
git commit --amend -m "Correct message"
```

---

## Undo last commit but keep changes

```bash
git reset --soft HEAD~1
```

---

## Discard all local changes

```bash
git reset --hard
```

---

## Accidentally staged everything

```bash
git restore --staged .
```

---

## See which branch you're on

```bash
git branch --show-current
```

---

## Download remote branches

```bash
git fetch --all
```

---

## Delete remote branch

```bash
git push origin --delete feature/login
```

---

## Force push (Use Carefully)

```bash
git push --force
```

Safer option:

```bash
git push --force-with-lease
```

---

# Best Practices

✅ Commit often.

✅ Write meaningful commit messages.

✅ Pull before starting work.

✅ Create a feature branch for each task.

✅ Never commit secrets.

✅ Prefer `git switch` over `checkout` for switching branches.

✅ Prefer `git restore` over older checkout syntax for restoring files.

✅ Use `--force-with-lease` instead of `--force` whenever possible.

✅ Fetch regularly to stay up to date with remote branches.
