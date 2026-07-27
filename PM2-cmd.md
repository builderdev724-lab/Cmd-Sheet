# PM2 Command Cheat Sheet

> A complete guide to PM2 commands for managing Node.js applications.

---

# Table of Contents

1. Installation
2. Starting Applications
3. Viewing Processes
4. Managing Processes
5. Logs
6. Monitoring
7. Startup & Auto Restart
8. Ecosystem File
9. Cluster Mode
10. Deployment
11. Useful Commands
12. Common Problems
13. Developer Workflow
14. Essential Commands
15. Best Practices

---

# 1. Installation

Install PM2 Globally

```bash
npm install -g pm2
```

Check Version

```bash
pm2 --version
```

---

# 2. Starting Applications

Start JavaScript App

```bash
pm2 start app.js
```

Start TypeScript (compiled)

```bash
pm2 start dist/main.js
```

Start with Name

```bash
pm2 start dist/main.js --name api
```

Start npm Script

```bash
pm2 start npm --name frontend -- start
```

Start Multiple Instances

```bash
pm2 start dist/main.js -i 4
```

Start Maximum CPU Cores

```bash
pm2 start dist/main.js -i max
```

---

# 3. Viewing Processes

List Applications

```bash
pm2 list
```

Detailed Information

```bash
pm2 show api
```

Describe Process

```bash
pm2 describe api
```

---

# 4. Managing Processes

Stop

```bash
pm2 stop api
```

Restart

```bash
pm2 restart api
```

Reload (Zero Downtime)

```bash
pm2 reload api
```

Delete Process

```bash
pm2 delete api
```

Delete All

```bash
pm2 delete all
```

Restart All

```bash
pm2 restart all
```

Stop All

```bash
pm2 stop all
```

---

# 5. Logs

View Logs

```bash
pm2 logs
```

Logs for One App

```bash
pm2 logs api
```

Clear Logs

```bash
pm2 flush
```

Open Log Files

```bash
~/.pm2/logs/
```

---

# 6. Monitoring

Real-Time Dashboard

```bash
pm2 monit
```

CPU & Memory

```bash
pm2 show api
```

---

# 7. Startup & Auto Restart

Generate Startup Script

```bash
pm2 startup
```

Save Running Processes

```bash
pm2 save
```

Restore Saved Processes

```bash
pm2 resurrect
```

---

# 8. Ecosystem File

Create Ecosystem File

```bash
pm2 init simple
```

Start Using Ecosystem

```bash
pm2 start ecosystem.config.js
```

Example

```javascript
module.exports = {
  apps: [
    {
      name: "api",
      script: "./dist/main.js",
      instances: "max",
      exec_mode: "cluster",
      env: {
        NODE_ENV: "production"
      }
    }
  ]
};
```

---

# 9. Cluster Mode

Run in Cluster Mode

```bash
pm2 start dist/main.js -i max
```

Reload Without Downtime

```bash
pm2 reload all
```

---

# 10. Deployment

Start Production

```bash
pm2 start ecosystem.config.js --env production
```

Save Configuration

```bash
pm2 save
```

---

# 11. Useful Commands

System Information

```bash
pm2 report
```

Kill PM2 Daemon

```bash
pm2 kill
```

Update PM2

```bash
pm2 update
```

Reset Restart Counter

```bash
pm2 reset api
```

---

# 12. Common Problems

Application Not Starting

```bash
pm2 logs api
```

Restart Application

```bash
pm2 restart api
```

Delete and Recreate

```bash
pm2 delete api
pm2 start dist/main.js --name api
```

---

# 13. Developer Workflow

Build Application

```bash
npm run build
```

Start

```bash
pm2 start dist/main.js --name api
```

Monitor

```bash
pm2 monit
```

Save Configuration

```bash
pm2 save
```

Enable Startup

```bash
pm2 startup
```

---

# 14. Essential Commands

```bash
pm2 start
pm2 stop
pm2 restart
pm2 reload
pm2 delete
pm2 list
pm2 show
pm2 logs
pm2 monit
pm2 save
pm2 startup
pm2 resurrect
pm2 report
pm2 update
pm2 kill
```

---

# 15. Best Practices

- Use meaningful process names with `--name`.
- Use cluster mode (`-i max`) for CPU-intensive production workloads.
- Prefer `pm2 reload` over `restart` for zero-downtime deployments.
- Always run `pm2 save` after changing your process list.
- Configure `pm2 startup` so applications restart automatically after a server reboot.
- Monitor memory and CPU usage regularly using `pm2 monit`.
- Store environment variables in an ecosystem file or your deployment environment rather than hardcoding them.