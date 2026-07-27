# Linux Command Cheat Sheet

> A comprehensive guide to essential Linux commands for developers.

---

# Table of Contents

1. Terminal Basics
2. Navigation
3. File & Directory Management
4. Viewing Files
5. Searching
6. File Permissions
7. Process Management
8. Disk Usage
9. Networking
10. Package Management (Ubuntu/Debian)
11. Compression
12. Environment Variables
13. Services
14. Users & Groups
15. Logs
16. System Information
17. Keyboard Shortcuts
18. Common Problems
19. Developer Workflow
20. Best Practices

---

# 1. Terminal Basics

## Print Current Directory

```bash
pwd
```

Use when:
- You want to know your current location.

Example

```bash
/home/priyojeet/projects/api
```

---

## Clear Terminal

```bash
clear
```

Shortcut

```text
Ctrl + L
```

---

## Command History

```bash
history
```

Search history

```text
Ctrl + R
```

---

# 2. Navigation

## List Files

```bash
ls
```

---

## Detailed List

```bash
ls -l
```

---

## Show Hidden Files

```bash
ls -a
```

---

## Human Readable Sizes

```bash
ls -lh
```

---

## Change Directory

```bash
cd folder-name
```

Go home

```bash
cd
```

Go back

```bash
cd ..
```

Previous folder

```bash
cd -
```

Root

```bash
cd /
```

---

# 3. File & Directory Management

## Create Folder

```bash
mkdir docs
```

Nested folders

```bash
mkdir -p src/components/ui
```

---

## Create File

```bash
touch app.js
```

Multiple files

```bash
touch a.txt b.txt c.txt
```

---

## Copy File

```bash
cp file.txt backup.txt
```

Copy folder

```bash
cp -r src backup
```

---

## Move/Rename

```bash
mv old.txt new.txt
```

Move folder

```bash
mv src app
```

---

## Delete File

```bash
rm file.txt
```

Delete folder

```bash
rm -r folder
```

Force delete

```bash
rm -rf folder
```

⚠️ Be careful with `rm -rf`.

---

# 4. Viewing Files

## Display File

```bash
cat file.txt
```

---

## View Large Files

```bash
less file.txt
```

Quit:

```text
q
```

---

## First Lines

```bash
head file.txt
```

10 lines

```bash
head -10 file.txt
```

---

## Last Lines

```bash
tail file.txt
```

Live logs

```bash
tail -f app.log
```

---

# 5. Searching

## Find Files

```bash
find . -name "*.ts"
```

---

## Search Text

```bash
grep "invoice" app.ts
```

Recursive

```bash
grep -r "TODO" .
```

Ignore case

```bash
grep -i "error" log.txt
```

---

## Locate File

```bash
locate package.json
```

Update database

```bash
sudo updatedb
```

---

# 6. File Permissions

View permissions

```bash
ls -l
```

Example

```text
-rwxr-xr--
```

---

Make executable

```bash
chmod +x script.sh
```

---

Change permissions

```bash
chmod 755 script.sh
```

---

Change owner

```bash
sudo chown user:user file.txt
```

---

# 7. Process Management

Running processes

```bash
ps
```

All processes

```bash
ps aux
```

---

Live monitor

```bash
top
```

Better monitor

```bash
htop
```

---

Kill process

```bash
kill PID
```

Force kill

```bash
kill -9 PID
```

Kill by name

```bash
killall node
```

---

# 8. Disk Usage

Disk usage

```bash
df -h
```

Folder size

```bash
du -sh .
```

Largest folders

```bash
du -h --max-depth=1
```

---

# 9. Networking

Ping

```bash
ping google.com
```

---

Download file

```bash
wget URL
```

---

HTTP request

```bash
curl https://example.com
```

---

IP Address

```bash
ip addr
```

---

Open ports

```bash
ss -tulpn
```

---

Hostname

```bash
hostname
```

---

# 10. Package Management (Ubuntu)

Update package list

```bash
sudo apt update
```

Upgrade packages

```bash
sudo apt upgrade
```

Install package

```bash
sudo apt install git
```

Remove package

```bash
sudo apt remove git
```

Remove unused packages

```bash
sudo apt autoremove
```

Clean cache

```bash
sudo apt clean
```

Search package

```bash
apt search docker
```

---

# 11. Compression

Create zip

```bash
zip archive.zip file.txt
```

Extract zip

```bash
unzip archive.zip
```

Create tar.gz

```bash
tar -czvf backup.tar.gz folder/
```

Extract

```bash
tar -xzvf backup.tar.gz
```

---

# 12. Environment Variables

Show variables

```bash
printenv
```

Specific variable

```bash
echo $HOME
```

Create variable

```bash
export APP_ENV=development
```

Remove

```bash
unset APP_ENV
```

---

# 13. Services

Status

```bash
systemctl status nginx
```

Start

```bash
sudo systemctl start nginx
```

Stop

```bash
sudo systemctl stop nginx
```

Restart

```bash
sudo systemctl restart nginx
```

Enable on boot

```bash
sudo systemctl enable nginx
```

---

# 14. Users & Groups

Current user

```bash
whoami
```

Current ID

```bash
id
```

Groups

```bash
groups
```

Switch user

```bash
su username
```

---

# 15. Logs

System logs

```bash
journalctl
```

Follow logs

```bash
journalctl -f
```

Last boot

```bash
journalctl -b
```

---

# 16. System Information

Kernel

```bash
uname -r
```

Full system

```bash
uname -a
```

CPU

```bash
lscpu
```

Memory

```bash
free -h
```

Storage

```bash
lsblk
```

Operating System

```bash
cat /etc/os-release
```

---

# 17. Keyboard Shortcuts

| Shortcut | Description |
|-----------|-------------|
| Ctrl + C | Stop current process |
| Ctrl + Z | Suspend process |
| Ctrl + D | Exit shell |
| Ctrl + L | Clear screen |
| Ctrl + R | Search history |
| Tab | Auto-complete |
| ↑ / ↓ | Previous/Next command |

---

# 18. Common Problems

Permission denied

```bash
chmod +x file.sh
```

or

```bash
sudo command
```

---

Port already in use

```bash
sudo ss -tulpn
```

---

Disk full

```bash
df -h
du -sh *
```

---

Command not found

```bash
which command
```

Install missing package.

---

# 19. Developer Workflow

Update packages

```bash
sudo apt update && sudo apt upgrade
```

Go to project

```bash
cd ~/Projects/api
```

Check Git

```bash
git status
```

Install packages

```bash
npm install
```

Run application

```bash
npm run dev
```

Monitor logs

```bash
tail -f logs/app.log
```

---

# 20. Best Practices

- Use `pwd` if you're unsure where you are.
- Use `ls -lah` to inspect directories.
- Prefer `cp -r` over manually copying folders.
- Double-check before running `rm -rf`.
- Use `history` and `Ctrl + R` to reuse commands.
- Learn `grep`, `find`, and `curl`; they are used daily.
- Keep your system updated with `sudo apt update` and `sudo apt upgrade`.
- Use `less` instead of `cat` for large files.
- Use `tail -f` to monitor log files in real time.
