# NestJS Command Cheat Sheet

> A complete guide to NestJS CLI commands for developers.

---

# Table of Contents

1. Installation
2. Create Project
3. Development
4. Generate Resources
5. Build
6. Testing
7. Dependency Management
8. Configuration
9. Debugging
10. Production
11. Common Problems
12. Developer Workflow
13. Essential Commands
14. Best Practices

---

# 1. Installation

Install Nest CLI

```bash
npm install -g @nestjs/cli
```

Check Version

```bash
nest --version
```

---

# 2. Create Project

Create Project

```bash
nest new my-api
```

Using npm

```bash
nest new my-api --package-manager npm
```

Using pnpm

```bash
nest new my-api --package-manager pnpm
```

---

# 3. Development

Start Development Server

```bash
npm run start:dev
```

Watch Mode

```bash
nest start --watch
```

Normal Start

```bash
npm run start
```

Debug Mode

```bash
npm run start:debug
```

---

# 4. Generate Resources

Generate Module

```bash
nest generate module users
```

Shortcut

```bash
nest g mo users
```

---

Generate Controller

```bash
nest g controller users
```

Shortcut

```bash
nest g co users
```

---

Generate Service

```bash
nest g service users
```

Shortcut

```bash
nest g s users
```

---

Generate Resource (CRUD)

```bash
nest g resource users
```

This generates:

- Module
- Controller
- Service
- DTOs
- Entity

---

Generate Middleware

```bash
nest g middleware logger
```

---

Generate Guard

```bash
nest g guard auth
```

---

Generate Pipe

```bash
nest g pipe validation
```

---

Generate Interceptor

```bash
nest g interceptor logging
```

---

Generate Filter

```bash
nest g filter http-exception
```

---

Generate Decorator

```bash
nest g decorator roles
```

---

Generate Gateway (WebSocket)

```bash
nest g gateway chat
```

---

Generate Library

```bash
nest g library shared
```

---

Generate Application (Monorepo)

```bash
nest g app api
```

---

# 5. Build

Build Project

```bash
npm run build
```

CLI

```bash
nest build
```

---

# 6. Testing

Run Tests

```bash
npm test
```

Watch Tests

```bash
npm run test:watch
```

Coverage

```bash
npm run test:cov
```

End-to-End Tests

```bash
npm run test:e2e
```

---

# 7. Dependency Management

Install Package

```bash
npm install package-name
```

Install Dev Dependency

```bash
npm install -D package-name
```

---

# 8. Configuration

Create Config Module

```bash
nest g module config
```

Install Config Package

```bash
npm install @nestjs/config
```

---

# 9. Debugging

Verbose Logs

```bash
npm run start:debug
```

Show CLI Help

```bash
nest --help
```

Project Information

```bash
nest info
```

---

# 10. Production

Build

```bash
npm run build
```

Run Production

```bash
node dist/main.js
```

Or

```bash
npm run start:prod
```

---

# 11. Common Problems

Delete Build Folder

Linux/macOS

```bash
rm -rf dist
```

Windows PowerShell

```powershell
Remove-Item dist -Recurse -Force
```

Rebuild

```bash
npm run build
```

Reinstall Dependencies

```bash
rm -rf node_modules package-lock.json
npm install
```

---

# 12. Developer Workflow

Create Project

```bash
nest new api
```

Generate Module

```bash
nest g mo auth
```

Generate Controller

```bash
nest g co auth
```

Generate Service

```bash
nest g s auth
```

Generate CRUD Resource

```bash
nest g resource users
```

Start Development

```bash
npm run start:dev
```

Run Tests

```bash
npm test
```

Build

```bash
npm run build
```

Run Production

```bash
npm run start:prod
```

---

# 13. Essential Commands

```bash
nest new
nest g module
nest g controller
nest g service
nest g resource
nest g middleware
nest g guard
nest g pipe
nest g interceptor
nest g filter
nest g decorator
nest g gateway
nest g library
nest build
nest start
nest start --watch
nest info
nest --version
npm run start:dev
npm run start:prod
npm run build
npm test
```

---

# 14. Best Practices

- Use the Nest CLI to generate files for consistent structure.
- Group related code into modules.
- Prefer `nest g resource` for standard CRUD features.
- Use DTOs with `class-validator` for request validation.
- Store configuration in `.env` files using `@nestjs/config`.
- Run tests before committing changes.
- Build and test the production bundle before deployment.