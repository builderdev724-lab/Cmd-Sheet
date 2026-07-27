# Curl Command Cheat Sheet

> A complete guide to cURL for developers.

---

# Table of Contents

1. What is cURL?
2. Basic Requests
3. HTTP Methods
4. Headers
5. Sending Data
6. Authentication
7. File Download
8. File Upload
9. Cookies
10. Redirects
11. SSL
12. Debugging
13. REST API Examples
14. Common Problems
15. Developer Workflow
16. Essential Commands

---

# 1. What is cURL?

cURL (Client URL) is a command-line tool used to transfer data over HTTP, HTTPS, FTP, and many other protocols.

Common uses:

- Test APIs
- Download files
- Upload files
- Authenticate requests
- Debug web servers

---

# 2. Basic Requests

GET Request

```bash
curl https://example.com
```

Pretty Print JSON

```bash
curl https://jsonplaceholder.typicode.com/posts | jq .
```

---

# 3. HTTP Methods

GET

```bash
curl https://api.example.com/users
```

POST

```bash
curl -X POST https://api.example.com/users
```

PUT

```bash
curl -X PUT https://api.example.com/users/1
```

PATCH

```bash
curl -X PATCH https://api.example.com/users/1
```

DELETE

```bash
curl -X DELETE https://api.example.com/users/1
```

---

# 4. Headers

Add Header

```bash
curl \
-H "Content-Type: application/json" \
https://api.example.com
```

Multiple Headers

```bash
curl \
-H "Authorization: Bearer TOKEN" \
-H "Accept: application/json" \
https://api.example.com
```

---

# 5. Sending JSON

```bash
curl \
-X POST \
-H "Content-Type: application/json" \
-d '{
"name":"John",
"email":"john@example.com"
}' \
https://api.example.com/users
```

---

# 6. Authentication

Bearer Token

```bash
curl \
-H "Authorization: Bearer YOUR_TOKEN" \
https://api.example.com/profile
```

Basic Auth

```bash
curl -u username:password https://example.com
```

---

# 7. Download Files

Download

```bash
curl -O https://example.com/file.zip
```

Rename While Downloading

```bash
curl -o app.zip https://example.com/file.zip
```

Resume Download

```bash
curl -C - -O https://example.com/file.zip
```

---

# 8. Upload Files

Upload File

```bash
curl \
-F "file=@image.png" \
https://example.com/upload
```

Multiple Files

```bash
curl \
-F "file1=@a.jpg" \
-F "file2=@b.jpg" \
https://example.com/upload
```

---

# 9. Cookies

Save Cookies

```bash
curl -c cookies.txt https://example.com
```

Use Cookies

```bash
curl -b cookies.txt https://example.com
```

---

# 10. Redirects

Follow Redirects

```bash
curl -L https://example.com
```

---

# 11. SSL

Ignore SSL Errors

```bash
curl -k https://localhost:3000
```

⚠️ Only for development.

---

# 12. Debugging

Show Headers

```bash
curl -I https://example.com
```

Verbose Mode

```bash
curl -v https://example.com
```

Very Verbose

```bash
curl --trace-ascii debug.txt https://example.com
```

Show Response Code

```bash
curl -w "%{http_code}\n" https://example.com
```

---

# 13. REST API Examples

GET Users

```bash
curl http://localhost:3000/users
```

Create User

```bash
curl \
-X POST \
-H "Content-Type: application/json" \
-d '{"name":"John"}' \
http://localhost:3000/users
```

Update User

```bash
curl \
-X PUT \
-H "Content-Type: application/json" \
-d '{"name":"Jane"}' \
http://localhost:3000/users/1
```

Delete User

```bash
curl \
-X DELETE \
http://localhost:3000/users/1
```

---

# 14. Common Problems

404 Not Found

Check:

- URL
- Route
- HTTP Method

401 Unauthorized

Check:

- Token
- Credentials
- Authorization Header

Connection Refused

Check:

- Server is running
- Correct port

SSL Certificate Error

Development only:

```bash
curl -k
```

---

# 15. Developer Workflow

Check Server

```bash
curl http://localhost:3000
```

Login

```bash
curl \
-X POST \
-H "Content-Type: application/json" \
-d '{"email":"admin@test.com","password":"password"}' \
http://localhost:3000/auth/login
```

Copy Token

Use it

```bash
curl \
-H "Authorization: Bearer TOKEN" \
http://localhost:3000/profile
```

---

# 16. Essential Commands

```bash
curl URL
curl -X POST
curl -H
curl -d
curl -O
curl -o
curl -F
curl -u
curl -I
curl -L
curl -v
curl -k
curl -w
curl -c
curl -b
```

---

# Best Practices

- Use HTTPS whenever possible.
- Store API tokens in environment variables.
- Use `-v` when debugging requests.
- Use `-I` to inspect response headers.
- Pipe JSON responses to `jq` for readability.
- Never expose API keys in shared scripts or repositories.