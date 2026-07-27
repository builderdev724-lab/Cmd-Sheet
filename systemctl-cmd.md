# systemctl Command Cheat Sheet

> A complete guide to managing Linux services with systemctl.

---

# Table of Contents

1. Introduction
2. Service Status
3. Start & Stop Services
4. Enable & Disable Services
5. Restart & Reload
6. Service Information
7. Boot & System Targets
8. Timers
9. Logs with journalctl
10. Common Services
11. Troubleshooting
12. Developer Workflow
13. Essential Commands
14. Best Practices

---

# 1. Introduction

Check systemd Version

```bash
systemctl --version
```

List Running Services

```bash
systemctl
```

List All Units

```bash
systemctl list-units
```

List Service Units

```bash
systemctl list-units --type=service
```

List Failed Services

```bash
systemctl --failed
```

---

# 2. Service Status

Check Status

```bash
systemctl status nginx
```

Examples

```bash
systemctl status docker
systemctl status postgresql
systemctl status redis-server
systemctl status ssh
```

---

# 3. Start & Stop Services

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

Reload Configuration

```bash
sudo systemctl reload nginx
```

Try Restart

```bash
sudo systemctl try-restart nginx
```

Reload or Restart

```bash
sudo systemctl reload-or-restart nginx
```

---

# 4. Enable & Disable Services

Enable at Boot

```bash
sudo systemctl enable nginx
```

Disable

```bash
sudo systemctl disable nginx
```

Enable Immediately

```bash
sudo systemctl enable --now nginx
```

Disable Immediately

```bash
sudo systemctl disable --now nginx
```

Check Enabled

```bash
systemctl is-enabled nginx
```

---

# 5. Restart & Reload

Reload systemd Configuration

```bash
sudo systemctl daemon-reload
```

Re-execute systemd

```bash
sudo systemctl daemon-reexec
```

---

# 6. Service Information

Show Service Details

```bash
systemctl show nginx
```

Show Dependencies

```bash
systemctl list-dependencies nginx
```

Check if Active

```bash
systemctl is-active nginx
```

---

# 7. Boot & System Targets

Current Target

```bash
systemctl get-default
```

Set Multi-user Target

```bash
sudo systemctl set-default multi-user.target
```

Set Graphical Target

```bash
sudo systemctl set-default graphical.target
```

Rescue Mode

```bash
sudo systemctl isolate rescue.target
```

---

# 8. Timers

List Timers

```bash
systemctl list-timers
```

Status

```bash
systemctl status my.timer
```

Start Timer

```bash
sudo systemctl start my.timer
```

---

# 9. Logs (journalctl)

Latest Logs

```bash
journalctl -u nginx
```

Live Logs

```bash
journalctl -fu nginx
```

Today's Logs

```bash
journalctl --since today
```

Boot Logs

```bash
journalctl -b
```

Previous Boot

```bash
journalctl -b -1
```

---

# 10. Common Services

Nginx

```bash
systemctl status nginx
```

Docker

```bash
systemctl status docker
```

PostgreSQL

```bash
systemctl status postgresql
```

Redis

```bash
systemctl status redis-server
```

SSH

```bash
systemctl status ssh
```

---

# 11. Common Problems

Service Won't Start

```bash
systemctl status service-name
```

View Logs

```bash
journalctl -xeu service-name
```

Reload Unit Files

```bash
sudo systemctl daemon-reload
```

Check Failed Services

```bash
systemctl --failed
```

---

# 12. Developer Workflow

Start Database

```bash
sudo systemctl start postgresql
```

Start Redis

```bash
sudo systemctl start redis-server
```

Start Nginx

```bash
sudo systemctl start nginx
```

Check Everything

```bash
systemctl --failed
```

Watch Logs

```bash
journalctl -fu nginx
```

---

# 13. Essential Commands

```bash
systemctl status
systemctl start
systemctl stop
systemctl restart
systemctl reload
systemctl enable
systemctl disable
systemctl is-active
systemctl is-enabled
systemctl show
systemctl list-units
systemctl --failed
systemctl daemon-reload

journalctl -u
journalctl -fu
journalctl -xeu
```

---

# 14. Best Practices

- Always check `systemctl status` before troubleshooting.
- Use `journalctl` to inspect service logs.
- Prefer `reload` over `restart` when supported to minimize downtime.
- Run `daemon-reload` after modifying service unit files.
- Enable essential services (`nginx`, `docker`, `postgresql`, `redis-server`) to start automatically on boot.
- Periodically check for failed services with `systemctl --failed`.