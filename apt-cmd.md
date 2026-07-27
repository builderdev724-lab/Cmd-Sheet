# APT Command Cheat Sheet

> A complete guide to Ubuntu's Advanced Package Tool (APT).

---

# Table of Contents

1. Package Information
2. Update Packages
3. Install Packages
4. Upgrade Packages
5. Remove Packages
6. Search Packages
7. Package Details
8. Repository Management
9. Cache Management
10. Dependencies
11. Download Packages
12. Troubleshooting
13. Developer Workflow
14. Essential Commands
15. Best Practices

---

# 1. Package Information

Update Package Index

```bash
sudo apt update
```

Upgrade Installed Packages

```bash
sudo apt upgrade
```

Full Upgrade

```bash
sudo apt full-upgrade
```

APT Version

```bash
apt --version
```

---

# 2. Install Packages

Install Package

```bash
sudo apt install nginx
```

Install Multiple Packages

```bash
sudo apt install git curl wget
```

Reinstall Package

```bash
sudo apt install --reinstall nginx
```

Install Specific Version

```bash
sudo apt install nginx=1.24.0-*
```

Install Without Recommended Packages

```bash
sudo apt install --no-install-recommends package-name
```

---

# 3. Upgrade Packages

Upgrade One Package

```bash
sudo apt install --only-upgrade nginx
```

Upgrade Everything

```bash
sudo apt upgrade
```

Distribution Upgrade

```bash
sudo apt full-upgrade
```

---

# 4. Remove Packages

Remove Package

```bash
sudo apt remove nginx
```

Remove with Configuration

```bash
sudo apt purge nginx
```

Remove Unused Packages

```bash
sudo apt autoremove
```

Clean Downloaded Packages

```bash
sudo apt autoclean
```

Clean Entire Cache

```bash
sudo apt clean
```

---

# 5. Search Packages

Search by Name

```bash
apt search redis
```

Exact Search

```bash
apt list redis*
```

Installed Packages

```bash
apt list --installed
```

Upgradeable Packages

```bash
apt list --upgradable
```

---

# 6. Package Details

Show Package Info

```bash
apt show nginx
```

Show Dependencies

```bash
apt depends nginx
```

Show Reverse Dependencies

```bash
apt rdepends nginx
```

Find Package Owner

```bash
dpkg -S /usr/bin/nginx
```

List Installed Files

```bash
dpkg -L nginx
```

---

# 7. Repository Management

Repository Files

```text
/etc/apt/sources.list
/etc/apt/sources.list.d/
```

Update After Repository Changes

```bash
sudo apt update
```

---

# 8. Cache Management

Download Package Only

```bash
apt download nginx
```

Clean Cache

```bash
sudo apt clean
```

Auto Clean

```bash
sudo apt autoclean
```

---

# 9. Dependencies

Fix Broken Dependencies

```bash
sudo apt --fix-broken install
```

Install Missing Dependencies

```bash
sudo apt install -f
```

---

# 10. Download Packages

Download Without Installing

```bash
apt download package-name
```

Download Source Package

```bash
apt source package-name
```

---

# 11. Troubleshooting

Package Not Found

```bash
sudo apt update
```

Fix Interrupted Installation

```bash
sudo dpkg --configure -a
```

Fix Broken Packages

```bash
sudo apt --fix-broken install
```

Repair Dependencies

```bash
sudo apt install -f
```

---

# 12. Developer Workflow

Update Package Lists

```bash
sudo apt update
```

Upgrade System

```bash
sudo apt upgrade
```

Install Development Tools

```bash
sudo apt install git curl wget build-essential
```

Install Database

```bash
sudo apt install postgresql
```

Install Web Server

```bash
sudo apt install nginx
```

Remove Unused Packages

```bash
sudo apt autoremove
```

---

# 13. Essential Commands

```bash
sudo apt update
sudo apt upgrade
sudo apt full-upgrade

sudo apt install
sudo apt remove
sudo apt purge

sudo apt autoremove
sudo apt autoclean
sudo apt clean

apt search
apt show
apt list --installed
apt list --upgradable

sudo apt --fix-broken install
sudo dpkg --configure -a
```

---

# 14. Best Practices

- Run `sudo apt update` before installing or upgrading packages.
- Use `sudo apt full-upgrade` only when necessary, as it may remove packages to resolve dependency changes.
- Use `sudo apt purge` if you want to remove configuration files along with a package.
- Regularly run `sudo apt autoremove` to remove unused dependencies.
- Use `apt search` and `apt show` to inspect packages before installing them.
- Keep third-party repositories to a minimum and only add trusted sources.