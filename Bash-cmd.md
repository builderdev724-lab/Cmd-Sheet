# Bash Command Cheat Sheet

> A complete guide to Bash commands and shell scripting for developers.

---

# Table of Contents

1. Bash Basics
2. Variables
3. Input & Output
4. Operators
5. Conditions
6. Loops
7. Functions
8. Arrays
9. String Operations
10. File Operations
11. Process Management
12. Pipes & Redirection
13. Command Substitution
14. Environment Variables
15. Useful Utilities
16. Debugging
17. Common Problems
18. Developer Workflow
19. Essential Commands
20. Best Practices

---

# 1. Bash Basics

Check Bash Version

```bash
bash --version
```

Run Script

```bash
bash script.sh
```

Make Executable

```bash
chmod +x script.sh
```

Run Executable Script

```bash
./script.sh
```

---

# 2. Variables

Create Variable

```bash
name="John"
```

Print Variable

```bash
echo "$name"
```

Read User Input

```bash
read name
```

Read with Prompt

```bash
read -p "Enter your name: " name
```

Read Password

```bash
read -s password
```

---

# 3. Input & Output

Print Text

```bash
echo "Hello"
```

Formatted Output

```bash
printf "Name: %s\n" "$name"
```

---

# 4. Operators

Arithmetic

```bash
a=$((10+5))
```

Comparison

```bash
[[ "$a" -gt 10 ]]
```

Logical AND

```bash
[[ "$a" -gt 5 && "$a" -lt 20 ]]
```

Logical OR

```bash
[[ "$a" -eq 5 || "$a" -eq 10 ]]
```

---

# 5. Conditions

If

```bash
if [[ -f app.js ]]; then
    echo "Exists"
fi
```

If Else

```bash
if [[ $age -ge 18 ]]; then
    echo "Adult"
else
    echo "Minor"
fi
```

Case

```bash
case $1 in
    start) echo "Starting";;
    stop) echo "Stopping";;
    *) echo "Unknown";;
esac
```

---

# 6. Loops

For Loop

```bash
for i in {1..5}; do
    echo $i
done
```

While Loop

```bash
count=1

while [[ $count -le 5 ]]; do
    echo $count
    ((count++))
done
```

Loop Through Files

```bash
for file in *.ts; do
    echo "$file"
done
```

---

# 7. Functions

Function

```bash
hello() {
    echo "Hello $1"
}
```

Call Function

```bash
hello Priyojeet
```

Return Value

```bash
return 0
```

---

# 8. Arrays

Create Array

```bash
langs=("JS" "TS" "Go")
```

Print All

```bash
echo "${langs[@]}"
```

First Item

```bash
echo "${langs[0]}"
```

Length

```bash
echo "${#langs[@]}"
```

---

# 9. String Operations

Length

```bash
echo "${#name}"
```

Substring

```bash
echo "${name:0:4}"
```

Replace

```bash
echo "${name/John/Alice}"
```

---

# 10. File Operations

Check File

```bash
[[ -f app.js ]]
```

Check Directory

```bash
[[ -d src ]]
```

Create File

```bash
touch app.js
```

Create Directory

```bash
mkdir logs
```

Delete File

```bash
rm file.txt
```

Delete Directory

```bash
rm -rf logs
```

---

# 11. Process Management

Run in Background

```bash
node app.js &
```

Jobs

```bash
jobs
```

Bring to Foreground

```bash
fg
```

Kill Process

```bash
kill PID
```

---

# 12. Pipes & Redirection

Redirect Output

```bash
echo "Hello" > file.txt
```

Append

```bash
echo "World" >> file.txt
```

Pipe

```bash
cat file.txt | grep Hello
```

Discard Output

```bash
command > /dev/null
```

---

# 13. Command Substitution

```bash
today=$(date)
```

Example

```bash
echo "$today"
```

---

# 14. Environment Variables

Show Variables

```bash
env
```

Export Variable

```bash
export NODE_ENV=production
```

Print Variable

```bash
echo "$NODE_ENV"
```

---

# 15. Useful Utilities

Find

```bash
find . -name "*.ts"
```

Grep

```bash
grep -R "UserService" src
```

Sort

```bash
sort names.txt
```

Unique

```bash
uniq file.txt
```

Count

```bash
wc -l file.txt
```

---

# 16. Debugging

Syntax Check

```bash
bash -n script.sh
```

Trace Execution

```bash
bash -x script.sh
```

Exit on Error

```bash
set -e
```

Treat Unset Variables as Errors

```bash
set -u
```

Pipeline Failure Detection

```bash
set -o pipefail
```

---

# 17. Common Problems

Permission Denied

```bash
chmod +x script.sh
```

Bad Interpreter

```bash
dos2unix script.sh
```

Check Syntax

```bash
bash -n script.sh
```

---

# 18. Developer Workflow

```bash
#!/usr/bin/env bash

set -euo pipefail

npm install
npm run build
npm test
npm run start
```

---

# 19. Essential Commands

```bash
bash
chmod +x
echo
printf
read
if
case
for
while
function
export
env
find
grep
sort
uniq
wc
kill
jobs
fg
set -e
set -u
set -o pipefail
bash -n
bash -x
```

---

# 20. Best Practices

- Start scripts with `#!/usr/bin/env bash`.
- Use `set -euo pipefail` for safer scripts.
- Always quote variables: `"$variable"`.
- Prefer `[[ ... ]]` over `[ ... ]`.
- Use functions to organize reusable logic.
- Check exit codes and handle errors explicitly.
- Keep scripts modular and well commented.
- Validate user input before using it.