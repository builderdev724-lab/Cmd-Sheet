# Nginx Command Cheat Sheet

> A complete guide to Nginx commands for developers and DevOps engineers.

---

# Table of Contents

1. Installation
2. Service Management
3. Configuration
4. Configuration Testing
5. Reload & Restart
6. Reverse Proxy
7. SSL/TLS
8. Logging
9. Compression
10. Load Balancing
11. Caching
12. Security
13. Debugging
14. Common Problems
15. Developer Workflow
16. Essential Commands
17. Best Practices

---

# 1. Installation

Ubuntu

```bash
sudo apt update
sudo apt install nginx
```

Check Version

```bash
nginx -v
```

Detailed Version

```bash
nginx -V
```

---

# 2. Service Management

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

Status

```bash
sudo systemctl status nginx
```

Enable on Boot

```bash
sudo systemctl enable nginx
```

Disable on Boot

```bash
sudo systemctl disable nginx
```

---

# 3. Configuration

Main Configuration

```text
/etc/nginx/nginx.conf
```

Sites Available

```text
/etc/nginx/sites-available/
```

Sites Enabled

```text
/etc/nginx/sites-enabled/
```

Create Site

```bash
sudo nano /etc/nginx/sites-available/myapp
```

Enable Site

```bash
sudo ln -s /etc/nginx/sites-available/myapp \
/etc/nginx/sites-enabled/
```

Disable Site

```bash
sudo rm /etc/nginx/sites-enabled/myapp
```

---

# 4. Configuration Testing

Test Configuration

```bash
sudo nginx -t
```

Verify Configuration

```bash
sudo nginx -T
```

---

# 5. Reload & Restart

Reload Without Downtime

```bash
sudo nginx -s reload
```

Graceful Stop

```bash
sudo nginx -s quit
```

Force Stop

```bash
sudo nginx -s stop
```

---

# 6. Reverse Proxy

Example

```nginx
server {
    listen 80;

    server_name example.com;

    location / {
        proxy_pass http://localhost:3000;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;

        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

---

# 7. SSL/TLS

Certificate Location

```text
/etc/ssl/
```

Example

```nginx
listen 443 ssl;

ssl_certificate /path/fullchain.pem;

ssl_certificate_key /path/privkey.pem;
```

---

# 8. Logging

Access Log

```text
/var/log/nginx/access.log
```

Error Log

```text
/var/log/nginx/error.log
```

Watch Logs

```bash
tail -f /var/log/nginx/error.log
```

---

# 9. Compression

Enable Gzip

```nginx
gzip on;

gzip_types text/css application/json application/javascript;
```

---

# 10. Load Balancing

```nginx
upstream backend {

    server localhost:3001;

    server localhost:3002;

}
```

Use Upstream

```nginx
proxy_pass http://backend;
```

---

# 11. Caching

Example

```nginx
proxy_cache my_cache;
```

Static Assets

```nginx
expires 30d;
```

---

# 12. Security

Hide Version

```nginx
server_tokens off;
```

Limit Upload Size

```nginx
client_max_body_size 20M;
```

---

# 13. Debugging

Validate Config

```bash
sudo nginx -t
```

Check Listening Ports

```bash
sudo ss -tulpn | grep nginx
```

Reload

```bash
sudo systemctl reload nginx
```

---

# 14. Common Problems

Port Already Used

```bash
sudo lsof -i :80
```

Permission Denied

```bash
sudo chown -R www-data:www-data /var/www
```

Restart

```bash
sudo systemctl restart nginx
```

View Logs

```bash
tail -f /var/log/nginx/error.log
```

---

# 15. Developer Workflow

Install

```bash
sudo apt install nginx
```

Create Site

```bash
sudo nano /etc/nginx/sites-available/myapp
```

Enable Site

```bash
sudo ln -s /etc/nginx/sites-available/myapp \
/etc/nginx/sites-enabled/
```

Test

```bash
sudo nginx -t
```

Reload

```bash
sudo systemctl reload nginx
```

Monitor

```bash
tail -f /var/log/nginx/access.log
```

---

# 16. Essential Commands

```bash
nginx -v
nginx -V
sudo nginx -t
sudo nginx -T
sudo nginx -s reload
sudo nginx -s stop
sudo nginx -s quit

sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl reload nginx
sudo systemctl status nginx

tail -f /var/log/nginx/error.log
tail -f /var/log/nginx/access.log
```

---

# 17. Best Practices

- Always run `sudo nginx -t` before reloading.
- Use HTTPS with valid SSL/TLS certificates.
- Keep configuration files modular using `sites-available` and `sites-enabled`.
- Enable gzip or Brotli compression for better performance.
- Hide the Nginx version using `server_tokens off`.
- Monitor access and error logs regularly.
- Use a reverse proxy for backend applications such as NestJS or Express.
- Set appropriate cache headers for static assets.