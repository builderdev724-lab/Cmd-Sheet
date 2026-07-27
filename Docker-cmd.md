# Docker Handbook

A complete Docker reference for developers.

---

# Table of Contents

1. What is Docker?
2. Docker Architecture
3. Installation
4. Docker Images
5. Docker Containers
6. Docker Volumes
7. Docker Networks
8. Dockerfile
9. Docker Compose
10. Docker Registry
11. Docker Desktop
12. Useful Commands
13. Debugging
14. Cleanup
15. Best Practices
16. Multi-stage Builds
17. Docker in Production
18. Common Problems
19. Docker + Node.js
20. Docker + PostgreSQL
21. Docker + Next.js
22. Docker + NestJS
23. Docker + Redis
24. Docker + Nginx
25. Docker Security
26. Docker Cheat Sheet

---

# 1. What is Docker?

Docker packages an application and all of its dependencies into a portable container.

Instead of:

"My project works on my computer."

Docker makes it:

"It works everywhere."

---

# 2. Docker Architecture

Docker Engine

↓

Docker Daemon

↓

Images

↓

Containers

↓

Volumes

↓

Networks

---

# 3. Installation

Check version

```bash
docker --version
```

---

Check Docker Compose

```bash
docker compose version
```

---

Check Docker information

```bash
docker info
```

---

# 4. Images

List images

```bash
docker images
```

---

Download image

```bash
docker pull postgres
```

---

Remove image

```bash
docker rmi postgres
```

---

Remove unused images

```bash
docker image prune
```

---

Remove everything unused

```bash
docker system prune -a
```

---

# 5. Containers

List running containers

```bash
docker ps
```

---

List all containers

```bash
docker ps -a
```

---

Create container

```bash
docker run nginx
```

---

Run in background

```bash
docker run -d nginx
```

---

Run with port mapping

```bash
docker run -p 3000:80 nginx
```

Host:Container

---

Name container

```bash
docker run --name web nginx
```

---

Stop container

```bash
docker stop web
```

---

Start container

```bash
docker start web
```

---

Restart container

```bash
docker restart web
```

---

Remove container

```bash
docker rm web
```

---

Force remove

```bash
docker rm -f web
```

---

# 6. Logs

View logs

```bash
docker logs web
```

---

Live logs

```bash
docker logs -f web
```

---

# 7. Execute Commands

Open shell

```bash
docker exec -it web bash
```

or

```bash
docker exec -it web sh
```

---

Check files

```bash
ls
```

---

# 8. Copy Files

Host → Container

```bash
docker cp app.js web:/app
```

---

Container → Host

```bash
docker cp web:/app .
```

---

# 9. Volumes

Create volume

```bash
docker volume create postgres-data
```

---

List volumes

```bash
docker volume ls
```

---

Inspect

```bash
docker volume inspect postgres-data
```

---

Delete

```bash
docker volume rm postgres-data
```

---

# 10. Networks

List

```bash
docker network ls
```

---

Create

```bash
docker network create backend
```

---

Connect

```bash
docker network connect backend web
```

---

Inspect

```bash
docker network inspect backend
```

---

# 11. Dockerfile

Example

```Dockerfile
FROM node:22-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "run", "start"]
```

Build

```bash
docker build -t myapp .
```

Run

```bash
docker run -p 3000:3000 myapp
```

---

# 12. Docker Compose

Start

```bash
docker compose up
```

Background

```bash
docker compose up -d
```

Stop

```bash
docker compose down
```

Rebuild

```bash
docker compose up --build
```

View services

```bash
docker compose ps
```

Logs

```bash
docker compose logs
```

---

# 13. Example Compose File

```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"

  postgres:
    image: postgres:17
    environment:
      POSTGRES_USER: admin
      POSTGRES_PASSWORD: password
      POSTGRES_DB: app

  redis:
    image: redis:7
```

---

# 14. Cleanup

Remove stopped containers

```bash
docker container prune
```

---

Remove unused volumes

```bash
docker volume prune
```

---

Remove unused networks

```bash
docker network prune
```

---

Remove everything

```bash
docker system prune -a
```

---

# 15. Debugging

Inspect container

```bash
docker inspect web
```

---

Resource usage

```bash
docker stats
```

---

Running processes

```bash
docker top web
```

---

# 16. Docker Registry

Login

```bash
docker login
```

---

Push image

```bash
docker push username/app
```

---

Pull image

```bash
docker pull username/app
```

---

# 17. Multi-stage Build

```Dockerfile
FROM node:22 AS builder

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build

FROM node:22-alpine

COPY --from=builder /app/dist ./dist

CMD ["node", "dist/main.js"]
```

---

# 18. Best Practices

✓ Use Alpine images

✓ Use .dockerignore

✓ Don't run as root

✓ Keep images small

✓ Use multi-stage builds

✓ Pin image versions

✓ Use environment variables

✓ Separate development and production

---

# 19. Common Problems

Port already in use

```bash
docker ps
```

Stop conflicting container.

---

Container exits immediately

```bash
docker logs container-name
```

---

Cannot connect to database

Check:

- Network
- Port
- Environment variables

---

No space left

```bash
docker system prune -a
```

---

# 20. Docker + Node.js

- Mount source code
- Use nodemon in development
- Ignore node_modules
- Use production image for deployment

---

# 21. Docker + PostgreSQL

Persist data using volumes.

```yaml
volumes:
  - postgres-data:/var/lib/postgresql/data
```

---

# 22. Docker + Redis

Expose port

```yaml
ports:
  - "6379:6379"
```

---

# 23. Docker + Nginx

Use as:

- Reverse proxy
- Static file server
- SSL termination
- Load balancer

---

# 24. Security

Never:

- Hardcode passwords
- Use latest tag in production
- Run as root
- Commit .env files

---

# 25. Useful Commands

Current containers

```bash
docker ps
```

Current images

```bash
docker images
```

Shell

```bash
docker exec -it container bash
```

Logs

```bash
docker logs -f container
```

Stats

```bash
docker stats
```

Cleanup

```bash
docker system prune -a
```
