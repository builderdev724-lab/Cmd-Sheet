# Next.js Command Cheat Sheet

> A complete guide to Next.js CLI commands for developers.

---

# Table of Contents

1. Installation
2. Create Project
3. Development
4. Production
5. Type Checking
6. Linting
7. Environment Variables
8. Debugging
9. Cache
10. Analyze Bundle
11. Deployment
12. Common Problems
13. Developer Workflow
14. Essential Commands
15. Best Practices

---

# 1. Installation

Create App

```bash
npx create-next-app@latest
```

With TypeScript

```bash
npx create-next-app@latest my-app --typescript
```

With Tailwind

```bash
npx create-next-app@latest my-app --tailwind
```

Using npm

```bash
npm create next@latest
```

---

# 2. Create Project

Move into Project

```bash
cd my-app
```

Install Dependencies

```bash
npm install
```

---

# 3. Development

Start Development Server

```bash
npm run dev
```

Using Turbopack

```bash
next dev --turbopack
```

Open

```
http://localhost:3000
```

---

# 4. Production

Build Project

```bash
npm run build
```

Start Production Server

```bash
npm run start
```

Production Build with Next CLI

```bash
next build
```

---

# 5. Type Checking

Type Check

```bash
tsc --noEmit
```

Lint Project

```bash
npm run lint
```

---

# 6. Environment Variables

Development

```
.env.local
```

Production

```
.env.production
```

View Variable

```bash
echo $NEXT_PUBLIC_API_URL
```

---

# 7. Debugging

Show Next Version

```bash
npx next --version
```

Project Information

```bash
npx next info
```

Verbose Build

```bash
next build --debug
```

---

# 8. Cache

Delete Cache

Linux/macOS

```bash
rm -rf .next
```

Windows PowerShell

```powershell
Remove-Item .next -Recurse -Force
```

Rebuild

```bash
npm run build
```

---

# 9. Analyze Bundle

Install Analyzer

```bash
npm install @next/bundle-analyzer
```

Build with Analyzer

```bash
ANALYZE=true npm run build
```

---

# 10. Deployment

Vercel

```bash
vercel
```

Build Docker Image

```bash
docker build -t next-app .
```

Start Docker

```bash
docker run -p 3000:3000 next-app
```

---

# 11. Common Problems

Delete node_modules

Linux/macOS

```bash
rm -rf node_modules package-lock.json
npm install
```

Port Already in Use

```bash
lsof -i :3000
```

or

```bash
ss -tulpn | grep 3000
```

Delete Cache

```bash
rm -rf .next
```

---

# 12. Developer Workflow

Install

```bash
npm install
```

Development

```bash
npm run dev
```

Lint

```bash
npm run lint
```

Type Check

```bash
tsc --noEmit
```

Build

```bash
npm run build
```

Production

```bash
npm run start
```

---

# 13. Essential Commands

```bash
npx create-next-app@latest
npm install
npm run dev
npm run build
npm run start
npm run lint
npx next --version
npx next info
rm -rf .next
tsc --noEmit
```

---

# 14. Best Practices

- Use the App Router for new projects.
- Keep `.env.local` out of version control.
- Run `npm run build` before pushing changes.
- Run `tsc --noEmit` to catch type errors.
- Delete the `.next` folder if you encounter cache-related issues.
- Use environment variables for API URLs and secrets.
- Test production builds locally before deploying.