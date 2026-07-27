# NPM Handbook

A complete reference for Node Package Manager (NPM).

---

# Table of Contents

1. Check Versions
2. Project Initialization
3. Installing Packages
4. Updating Packages
5. Removing Packages
6. Package Information
7. Running Scripts
8. Dependency Management
9. Security
10. Auditing
11. Cache
12. Troubleshooting
13. Publishing Packages
14. Workspaces
15. Performance
16. Useful Commands
17. Common Problems

---

# 1. Check Versions

## Check Node Version

```bash
node -v
```

---

## Check NPM Version

```bash
npm -v
```

---

## Environment Information

```bash
npm doctor
```

Checks:

- Node installation
- npm configuration
- Registry
- Cache
- Permissions

---

# 2. Initialize Project

Create package.json

```bash
npm init
```

---

Quick initialize

```bash
npm init -y
```

---

# 3. Installing Packages

Install dependency

```bash
npm install express
```

or

```bash
npm i express
```

---

Install dev dependency

```bash
npm install -D typescript
```

---

Install globally

```bash
npm install -g nodemon
```

---

Install exact version

```bash
npm install react@19.1.0
```

---

Install from package.json

```bash
npm install
```

---

# 4. Updating Packages

Update packages

```bash
npm update
```

---

Update one package

```bash
npm update express
```

---

Check outdated packages

```bash
npm outdated
```

Example:

Package | Current | Wanted | Latest

- Current = installed
- Wanted = satisfies package.json
- Latest = newest release

---

# 5. Removing Packages

Remove dependency

```bash
npm uninstall express
```

---

Remove global package

```bash
npm uninstall -g nodemon
```

---

# 6. Package Information

List installed packages

```bash
npm list
```

---

Top-level packages

```bash
npm list --depth=0
```

---

Global packages

```bash
npm list -g --depth=0
```

---

Package information

```bash
npm view express
```

---

Package versions

```bash
npm view express versions
```

---

Why package exists

```bash
npm explain express
```

---

# 7. Running Scripts

Run script

```bash
npm run dev
```

---

Production

```bash
npm run start
```

---

Build

```bash
npm run build
```

---

Test

```bash
npm test
```

---

See available scripts

```bash
npm run
```

---

# 8. Dependency Management

Install exactly from lockfile

```bash
npm ci
```

Best for:

- CI/CD
- Production
- Docker

---

Deduplicate packages

```bash
npm dedupe
```

---

Find duplicate packages

```bash
npm ls
```

---

# 9. Security

## Audit Project

```bash
npm audit
```

Shows:

- Vulnerabilities
- Severity
- Recommended fixes

---

Automatically fix

```bash
npm audit fix
```

---

Force fixes (breaking changes possible)

```bash
npm audit fix --force
```

---

Production only

```bash
npm audit --omit=dev
```

---

Generate JSON report

```bash
npm audit --json
```

---

# 10. Health Checks

Check package integrity

```bash
npm doctor
```

---

Verify cache

```bash
npm cache verify
```

---

Clear cache

```bash
npm cache clean --force
```

---

# 11. Dependency Analysis

Tree

```bash
npm ls
```

---

Specific package

```bash
npm ls react
```

---

Explain dependency

```bash
npm explain react
```

---

# 12. Troubleshooting

Delete node_modules

Linux/macOS

```bash
rm -rf node_modules
```

Windows PowerShell

```powershell
Remove-Item node_modules -Recurse -Force
```

---

Delete package lock

Linux/macOS

```bash
rm package-lock.json
```

Windows

```powershell
Remove-Item package-lock.json
```

---

Reinstall

```bash
npm install
```

---

Clean install

```bash
npm ci
```

---

# 13. Publishing

Login

```bash
npm login
```

---

Publish

```bash
npm publish
```

---

Unpublish

```bash
npm unpublish package-name
```

---

# 14. Workspaces

Install workspace dependency

```bash
npm install lodash -w packages/api
```

---

Run script in workspace

```bash
npm run build -w packages/web
```

---

Run in all workspaces

```bash
npm run build --workspaces
```

---

# 15. Performance

Install faster

```bash
npm ci
```

---

Skip optional dependencies

```bash
npm install --omit=optional
```

---

Production install

```bash
npm install --omit=dev
```

---

# 16. Useful Commands

Current registry

```bash
npm config get registry
```

---

Set registry

```bash
npm config set registry https://registry.npmjs.org/
```

---

Who am I

```bash
npm whoami
```

---

Search packages

```bash
npm search prisma
```

---

Open package homepage

```bash
npm home express
```

---

Open GitHub repository

```bash
npm repo express
```

---

# 17. Common Problems

Dependency conflicts

```bash
npm install --legacy-peer-deps
```

Use only when necessary.

---

Permission issues (Linux)

Avoid using `sudo npm install` for project dependencies.

Use a Node version manager such as `nvm` instead.

---

Corrupted node_modules

```bash
rm -rf node_modules package-lock.json
npm install
```

---

Package not found

```bash
npm config get registry
```

Verify the registry and package name.

---

Missing package after clone

```bash
npm install
```

---

Build failing after dependency update

```bash
npm ci
```

Restores the exact versions from `package-lock.json`.

---

# Commands Every Developer Should Know

```bash
npm -v
node -v
npm install
npm ci
npm outdated
npm update
npm audit
npm audit fix
npm doctor
npm list --depth=0
npm explain <package>
npm cache verify
npm cache clean --force
npm run dev
npm run build
npm run test
npm run lint
npm run format
```

---

# Best Practices

- Commit `package-lock.json` to version control.
- Use `npm ci` in CI/CD pipelines and Docker builds.
- Run `npm audit` regularly.
- Review `npm audit fix --force` changes before committing.
- Keep dependencies up to date with `npm outdated`.
- Prefer local project dependencies over global installs.
- Avoid deleting `package-lock.json` unless you intentionally want to regenerate it.
- Pin critical production dependencies to tested versions when appropriate.
