# Redis Command Cheat Sheet

> A complete guide to Redis CLI commands for developers.

---

# Table of Contents

1. Installation
2. Starting Redis
3. Redis CLI
4. String Commands
5. Key Commands
6. Hash Commands
7. List Commands
8. Set Commands
9. Sorted Set Commands
10. Expiration
11. Transactions
12. Pub/Sub
13. Persistence
14. Monitoring
15. Backup
16. Troubleshooting
17. Developer Workflow
18. Essential Commands
19. Best Practices

---

# 1. Installation

Ubuntu

```bash
sudo apt update
sudo apt install redis-server
```

Check Version

```bash
redis-server --version
```

---

# 2. Service Management

Start Redis

```bash
sudo systemctl start redis-server
```

Stop

```bash
sudo systemctl stop redis-server
```

Restart

```bash
sudo systemctl restart redis-server
```

Status

```bash
sudo systemctl status redis-server
```

Enable on Boot

```bash
sudo systemctl enable redis-server
```

---

# 3. Redis CLI

Open CLI

```bash
redis-cli
```

Connect Remote

```bash
redis-cli -h localhost -p 6379
```

Authenticate

```bash
AUTH password
```

Exit

```bash
exit
```

---

# 4. String Commands

Set Value

```bash
SET username "John"
```

Get Value

```bash
GET username
```

Delete

```bash
DEL username
```

Check Exists

```bash
EXISTS username
```

Increment

```bash
INCR counter
```

Decrement

```bash
DECR counter
```

---

# 5. Key Commands

Show Keys

```bash
KEYS *
```

Find by Pattern

```bash
KEYS user:*
```

Rename

```bash
RENAME oldKey newKey
```

Type

```bash
TYPE username
```

Database Size

```bash
DBSIZE
```

---

# 6. Hash Commands

Create

```bash
HSET user:1 name John
```

Read

```bash
HGET user:1 name
```

All Fields

```bash
HGETALL user:1
```

Delete Field

```bash
HDEL user:1 name
```

---

# 7. List Commands

Push Left

```bash
LPUSH queue task1
```

Push Right

```bash
RPUSH queue task2
```

Pop Left

```bash
LPOP queue
```

Pop Right

```bash
RPOP queue
```

List Items

```bash
LRANGE queue 0 -1
```

---

# 8. Set Commands

Add

```bash
SADD users Alice
```

Members

```bash
SMEMBERS users
```

Remove

```bash
SREM users Alice
```

---

# 9. Sorted Sets

Add

```bash
ZADD scores 100 Alice
```

List

```bash
ZRANGE scores 0 -1
```

Reverse

```bash
ZREVRANGE scores 0 -1
```

---

# 10. Expiration

Expire in Seconds

```bash
EXPIRE token 300
```

TTL

```bash
TTL token
```

Set with Expiry

```bash
SET session abc EX 3600
```

Remove Expiry

```bash
PERSIST token
```

---

# 11. Transactions

Start

```bash
MULTI
```

Execute

```bash
EXEC
```

Discard

```bash
DISCARD
```

---

# 12. Pub/Sub

Subscribe

```bash
SUBSCRIBE chat
```

Publish

```bash
PUBLISH chat "Hello"
```

---

# 13. Persistence

Save

```bash
SAVE
```

Background Save

```bash
BGSAVE
```

Last Save

```bash
LASTSAVE
```

---

# 14. Monitoring

Ping

```bash
PING
```

Memory

```bash
INFO memory
```

Server Info

```bash
INFO
```

Monitor Commands

```bash
MONITOR
```

---

# 15. Backup

Backup Database

```bash
BGSAVE
```

Redis Dump

```
dump.rdb
```

---

# 16. Common Problems

Redis Not Running

```bash
sudo systemctl status redis-server
```

Connection Failed

```bash
redis-cli ping
```

Expected

```
PONG
```

Clear Database

```bash
FLUSHDB
```

Clear Everything

```bash
FLUSHALL
```

---

# 17. Developer Workflow

Start Redis

```bash
sudo systemctl start redis-server
```

Connect

```bash
redis-cli
```

Check

```bash
PING
```

Cache Value

```bash
SET api:data "{}"
```

Retrieve

```bash
GET api:data
```

Exit

```bash
exit
```

---

# 18. Essential Commands

```bash
redis-server
redis-cli
PING
SET
GET
DEL
EXPIRE
TTL
KEYS *
HSET
HGETALL
LPUSH
RPUSH
LRANGE
SADD
SMEMBERS
ZADD
ZRANGE
MULTI
EXEC
SUBSCRIBE
PUBLISH
INFO
MONITOR
FLUSHDB
FLUSHALL
```

---

# 19. Best Practices

- Avoid using `KEYS *` in production; use `SCAN` for large datasets.
- Set expiration times for cache entries.
- Use Redis primarily as a cache or ephemeral store, not your primary database unless that's your design.
- Enable authentication for production deployments.
- Monitor memory usage with `INFO memory`.
- Back up important data if Redis persistence is enabled.