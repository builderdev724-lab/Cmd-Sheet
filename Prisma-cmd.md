# Prisma Command Cheat Sheet

> A complete guide to Prisma CLI commands for developers.

---

# Table of Contents

1. What is Prisma?
2. Installation
3. Project Setup
4. Generate Prisma Client
5. Migrations
6. Database Synchronization
7. Database Introspection
8. Prisma Studio
9. Validation & Formatting
10. Seeding
11. Production Commands
12. Troubleshooting
13. Developer Workflow
14. Essential Commands
15. Best Practices

---

# 1. What is Prisma?

Prisma is a modern ORM for Node.js and TypeScript.

It provides:

- Type-safe database access
- Database migrations
- Prisma Client
- Prisma Studio
- Database introspection

---

# 2. Installation

Install Prisma

```bash
npm install prisma --save-dev
```

Install Prisma Client

```bash
npm install @prisma/client
```

Check Version

```bash
npx prisma --version
```

---

# 3. Project Setup

Initialize Prisma

```bash
npx prisma init
```

Creates

```
prisma/
.env
schema.prisma
```

---

Initialize with PostgreSQL

```bash
npx prisma init --datasource-provider postgresql
```

---

# 4. Generate Prisma Client

Generate Client

```bash
npx prisma generate
```

Run after:

- Schema changes
- Installing Prisma Client
- Pulling database changes

---

# 5. Migrations

Create Migration

```bash
npx prisma migrate dev --name init
```

Example

```bash
npx prisma migrate dev --name add_users
```

Deploy Migrations

```bash
npx prisma migrate deploy
```

Reset Database

```bash
npx prisma migrate reset
```

View Migration Status

```bash
npx prisma migrate status
```

Resolve Migration

```bash
npx prisma migrate resolve
```

---

# 6. Database Synchronization

Push Schema

```bash
npx prisma db push
```

Updates database without creating migrations.

Good for:

- Prototypes
- Local development

Not recommended for production.

---

Pull Existing Database

```bash
npx prisma db pull
```

Updates schema.prisma from the database.

---

Push Then Generate

```bash
npx prisma db push
npx prisma generate
```

---

# 7. Database Introspection

Pull Schema

```bash
npx prisma db pull
```

Useful when:

- Database already exists
- Working with legacy projects

---

# 8. Prisma Studio

Open GUI

```bash
npx prisma studio
```

Features

- Browse tables
- Edit records
- Delete records
- Search data

---

# 9. Validation & Formatting

Validate Schema

```bash
npx prisma validate
```

Format Schema

```bash
npx prisma format
```

---

# 10. Seeding

Run Seed Script

```bash
npx prisma db seed
```

Example package.json

```json
{
  "prisma": {
    "seed": "tsx prisma/seed.ts"
  }
}
```

---

# 11. Production Commands

Deploy Migrations

```bash
npx prisma migrate deploy
```

Generate Client

```bash
npx prisma generate
```

Avoid using

```bash
npx prisma migrate dev
```

in production.

---

# 12. Troubleshooting

Migration Status

```bash
npx prisma migrate status
```

Database Connection

```bash
npx prisma db pull
```

Generate Client

```bash
npx prisma generate
```

Reset Database

```bash
npx prisma migrate reset
```

Validate Schema

```bash
npx prisma validate
```

---

# 13. Developer Workflow

Create Model

```prisma
model User {
  id    String @id @default(cuid())
  email String @unique
}
```

Create Migration

```bash
npx prisma migrate dev --name create_user
```

Generate Client

```bash
npx prisma generate
```

Open Studio

```bash
npx prisma studio
```

---

# 14. Essential Commands

```bash
npx prisma init
npx prisma generate
npx prisma migrate dev
npx prisma migrate deploy
npx prisma migrate reset
npx prisma migrate status
npx prisma db push
npx prisma db pull
npx prisma db seed
npx prisma validate
npx prisma format
npx prisma studio
npx prisma --version
```

---

# 15. Best Practices

- Always commit migration files.
- Run `prisma generate` after schema changes.
- Use `migrate dev` during development.
- Use `migrate deploy` in production.
- Use `db push` only for rapid prototyping.
- Store `DATABASE_URL` in `.env`.
- Run `prisma validate` before committing schema changes.
- Use Prisma Studio to inspect data instead of editing production databases directly.