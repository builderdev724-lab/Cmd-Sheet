# PostgreSQL Command Cheat Sheet

> A complete guide to PostgreSQL commands for developers.

---

# Table of Contents

1. What is PostgreSQL?
2. Installing PostgreSQL
3. Service Management
4. Connecting to PostgreSQL
5. Database Commands
6. User & Role Management
7. Table Commands
8. CRUD Operations
9. Querying Data
10. Import & Export
11. Backup & Restore
12. PostgreSQL CLI (psql)
13. Useful Meta Commands
14. Performance
15. Common Problems
16. Developer Workflow
17. Essential Commands

---

# 1. What is PostgreSQL?

PostgreSQL is an open-source relational database management system (RDBMS).

It is commonly used with:

- Node.js
- NestJS
- Prisma
- Django
- Laravel
- Spring Boot

---

# 2. Installing PostgreSQL

Ubuntu

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```

Check version

```bash
psql --version
```

---

# 3. Service Management

Start PostgreSQL

```bash
sudo systemctl start postgresql
```

Stop

```bash
sudo systemctl stop postgresql
```

Restart

```bash
sudo systemctl restart postgresql
```

Status

```bash
sudo systemctl status postgresql
```

Enable on Boot

```bash
sudo systemctl enable postgresql
```

---

# 4. Connecting to PostgreSQL

Switch to postgres user

```bash
sudo -u postgres psql
```

Connect as another user

```bash
psql -U username
```

Connect to a database

```bash
psql -U username -d database_name
```

Connect using host

```bash
psql -h localhost -U username -d database_name
```

Exit

```sql
\q
```

---

# 5. Database Commands

List databases

```sql
\l
```

Create database

```sql
CREATE DATABASE company_db;
```

Delete database

```sql
DROP DATABASE company_db;
```

Connect database

```sql
\c company_db
```

Current database

```sql
SELECT current_database();
```

---

# 6. User & Role Management

Create user

```sql
CREATE USER admin WITH PASSWORD 'password';
```

Grant privileges

```sql
GRANT ALL PRIVILEGES ON DATABASE company_db TO admin;
```

List users

```sql
\du
```

Change password

```sql
ALTER USER admin PASSWORD 'newpassword';
```

Delete user

```sql
DROP USER admin;
```

---

# 7. Table Commands

Show tables

```sql
\dt
```

Describe table

```sql
\d users
```

Create table

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name TEXT,
    email TEXT UNIQUE
);
```

Delete table

```sql
DROP TABLE users;
```

Rename table

```sql
ALTER TABLE users RENAME TO customers;
```

---

# 8. CRUD Operations

Insert

```sql
INSERT INTO users(name,email)
VALUES ('John','john@example.com');
```

Read

```sql
SELECT * FROM users;
```

Update

```sql
UPDATE users
SET name='Jane'
WHERE id=1;
```

Delete

```sql
DELETE FROM users
WHERE id=1;
```

---

# 9. Querying Data

Filter

```sql
SELECT * FROM users
WHERE id=1;
```

Order

```sql
SELECT * FROM users
ORDER BY id DESC;
```

Limit

```sql
SELECT * FROM users
LIMIT 10;
```

Count

```sql
SELECT COUNT(*) FROM users;
```

Distinct

```sql
SELECT DISTINCT name FROM users;
```

---

# 10. Import & Export

Export database

```bash
pg_dump database_name > backup.sql
```

Restore

```bash
psql database_name < backup.sql
```

Export custom format

```bash
pg_dump -Fc database_name > backup.dump
```

Restore custom backup

```bash
pg_restore -d database_name backup.dump
```

---

# 11. Backup & Restore

Backup all databases

```bash
pg_dumpall > all.sql
```

Restore

```bash
psql -f all.sql postgres
```

---

# 12. PostgreSQL CLI

Launch

```bash
psql
```

Help

```sql
\?
```

SQL help

```sql
\h
```

---

# 13. Useful Meta Commands

| Command | Description |
|----------|-------------|
| \l | List databases |
| \c | Connect database |
| \dt | List tables |
| \d table | Describe table |
| \du | List users |
| \dn | List schemas |
| \df | List functions |
| \q | Quit |

---

# 14. Performance

Explain query

```sql
EXPLAIN
SELECT * FROM users;
```

Analyze query

```sql
EXPLAIN ANALYZE
SELECT * FROM users;
```

---

# 15. Common Problems

Cannot connect

Check service

```bash
sudo systemctl status postgresql
```

Wrong password

```sql
ALTER USER admin PASSWORD 'newpassword';
```

Permission denied

```sql
GRANT ALL PRIVILEGES
ON DATABASE company_db
TO admin;
```

---

# 16. Developer Workflow

Start PostgreSQL

```bash
sudo systemctl start postgresql
```

Connect

```bash
psql -U postgres
```

Create database

```sql
CREATE DATABASE app;
```

Connect

```sql
\c app
```

List tables

```sql
\dt
```

Exit

```sql
\q
```

---

# 17. Essential Commands

```bash
psql
pg_dump
pg_restore
createdb
dropdb
createuser
dropuser
vacuumdb
reindexdb
```

---

# Best Practices

- Use strong passwords for database users.
- Back up databases regularly with `pg_dump`.
- Create separate users for development and production.
- Use `EXPLAIN ANALYZE` to optimize slow queries.
- Grant only the permissions required by each application.
- Never expose your PostgreSQL port directly to the public internet unless properly secured.