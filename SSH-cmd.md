# SSH Command Cheat Sheet

> A complete guide to Secure Shell (SSH) commands for developers.

---

# Table of Contents

1. What is SSH?
2. Generate SSH Keys
3. Manage SSH Keys
4. Connect to Remote Servers
5. Copy Files
6. SSH Config
7. GitHub SSH
8. SSH Agent
9. Port Forwarding
10. Debugging
11. Security Best Practices
12. Common Problems
13. Developer Workflow
14. Essential Commands

---

# 1. What is SSH?

SSH (Secure Shell) is a secure protocol used to:

- Connect to remote servers
- Access cloud instances
- Push and pull from GitHub
- Transfer files securely
- Execute remote commands

Default Port

```
22
```

---

# 2. Generate SSH Keys

Generate Ed25519 Key (Recommended)

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

Generate RSA Key

```bash
ssh-keygen -t rsa -b 4096 -C "your@email.com"
```

Keys are usually stored in

```text
~/.ssh/
```

Example

```
id_ed25519
id_ed25519.pub
```

---

# 3. View Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy this to GitHub, GitLab, or your server.

---

# 4. Connect to a Server

```bash
ssh username@server-ip
```

Example

```bash
ssh ubuntu@192.168.1.20
```

Using Port

```bash
ssh -p 2222 ubuntu@192.168.1.20
```

Using Identity File

```bash
ssh -i ~/.ssh/id_ed25519 ubuntu@192.168.1.20
```

---

# 5. SSH Agent

Start Agent

```bash
eval "$(ssh-agent -s)"
```

Add Key

```bash
ssh-add ~/.ssh/id_ed25519
```

List Loaded Keys

```bash
ssh-add -l
```

Remove All Keys

```bash
ssh-add -D
```

---

# 6. Test GitHub SSH

```bash
ssh -T git@github.com
```

Successful output

```
Hi username! You've successfully authenticated.
```

---

# 7. Copy Files

Copy Local → Server

```bash
scp file.txt user@server:/home/user/
```

Copy Folder

```bash
scp -r project user@server:/home/user/
```

Copy Server → Local

```bash
scp user@server:/home/user/file.txt .
```

Specify Port

```bash
scp -P 2222 file.txt user@server:/home/user/
```

---

# 8. SSH Config

Location

```text
~/.ssh/config
```

Example

```text
Host myserver
    HostName 192.168.1.20
    User ubuntu
    Port 22
    IdentityFile ~/.ssh/id_ed25519
```

Now connect with

```bash
ssh myserver
```

---

# 9. Port Forwarding

Local Port Forwarding

```bash
ssh -L 8080:localhost:80 user@server
```

Remote Port Forwarding

```bash
ssh -R 8080:localhost:3000 user@server
```

Dynamic SOCKS Proxy

```bash
ssh -D 8080 user@server
```

---

# 10. Run Remote Commands

```bash
ssh user@server "ls -la"
```

Restart Nginx

```bash
ssh user@server "sudo systemctl restart nginx"
```

---

# 11. Debugging

Verbose Output

```bash
ssh -v user@server
```

More Details

```bash
ssh -vv user@server
```

Maximum Debugging

```bash
ssh -vvv user@server
```

---

# 12. Useful Commands

List SSH Files

```bash
ls ~/.ssh
```

Check Fingerprint

```bash
ssh-keygen -lf ~/.ssh/id_ed25519.pub
```

Remove Old Host Key

```bash
ssh-keygen -R hostname
```

Known Hosts

```bash
cat ~/.ssh/known_hosts
```

---

# 13. Security Best Practices

- Use Ed25519 keys.
- Disable password login on production servers.
- Never share private keys.
- Set a passphrase on your SSH key.
- Use different keys for personal and work accounts.
- Restrict permissions:

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_ed25519
chmod 644 ~/.ssh/id_ed25519.pub
```

---

# 14. Common Problems

Permission Denied

```bash
chmod 600 ~/.ssh/id_ed25519
```

Connection Refused

Check

```bash
sudo systemctl status ssh
```

Wrong Host Key

```bash
ssh-keygen -R hostname
```

Test Connection

```bash
ssh -T git@github.com
```

---

# 15. Developer Workflow

Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "you@example.com"
```

Start Agent

```bash
eval "$(ssh-agent -s)"
```

Add Key

```bash
ssh-add ~/.ssh/id_ed25519
```

Copy Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

Add it to GitHub.

Test

```bash
ssh -T git@github.com
```

Clone Repository

```bash
git clone git@github.com:user/repo.git
```

---

# 16. Essential Commands

```bash
ssh
ssh-keygen
ssh-add
ssh-agent
scp
sftp
ssh-copy-id
ssh -T git@github.com
ssh -v
ssh -L
ssh -R
```