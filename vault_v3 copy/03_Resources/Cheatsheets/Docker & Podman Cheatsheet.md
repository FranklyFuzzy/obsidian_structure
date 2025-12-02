---
type:
  - resource
status:
  - reference
tags:
  - docker
  - cheatsheet
created: 2025-12-02
updated: 2025-12-02
---

This is a general-purpose cheatsheet for **Docker, Podman, Docker Compose, and Podman Compose**, including container update workflows.  
Tailored for multi-service setups like home-labs, with persistent volumes and `.env` usage.


For local files
start
run `docker compose up -d`
stop
When done: `docker compose down`
access: [http://localhost:8080](http://localhost:8080/)

For updating - from the correct container folder path:
`docker compose pull`
Pulls **latest image** for all services in your Compose file
Or just one service:
`docker compose pull gitea`
Stop the old container
`docker compose down`
Recreate and start updated container
`docker compose up -d`

---

## 1️⃣ Basic Commands

### Check versions
```bash
docker --version
podman --version
````

### List containers

```bash
docker ps           # running
docker ps -a        # all, including stopped
podman ps
podman ps -a
```

### List images

```bash
docker images
podman images
```

---

## 2️⃣ Working with Containers

### Start / stop / restart

```bash
docker start <container>
docker stop <container>
docker restart <container>
podman start <container>
podman stop <container>
podman restart <container>
```

### Remove stopped containers

```bash
docker rm <container>
podman rm <container>
```

### Inspect / Exec

```bash
docker exec -it <container> bash   # enter container
podman exec -it <container> bash
docker inspect <container>         # detailed info
podman inspect <container>
```

---

## 3️⃣ Working with Images

### Pull / Remove / Build

```bash
docker pull image:tag
podman pull image:tag

docker rmi image:tag
podman rmi image:tag

docker build -t name:tag .
podman build -t name:tag .
```

---

## 4️⃣ Logs & Debugging

```bash
docker logs -f <container>       # follow logs
docker logs --tail 50 <container>  # last 50 lines
podman logs -f <container>
```

---

## 5️⃣ System Cleanup

```bash
docker container prune
podman container prune
docker image prune
podman image prune
docker system prune -a
podman system prune -a
```

---

## 6️⃣ Networking

```bash
docker network ls
podman network ls
docker port <container>
podman port <container>
```

---

## 7️⃣ Volumes

```bash
docker volume ls
podman volume ls
docker volume inspect <volume>
podman volume inspect <volume>
docker volume prune
podman volume prune
```

---

## 8️⃣ Docker Compose (Multi-Service)

```bash
docker compose up -d                  # start all services
docker compose up -d --build          # rebuild images
docker compose pull                    # pull latest images
docker compose down                    # stop/remove containers
docker compose logs -f <service>      # view logs
docker compose ps                      # list services
docker compose build <service>         # rebuild single service
docker compose up -d <service>        # update single service
```

---

## 9️⃣ Podman Compose

```bash
podman-compose up -d
podman-compose up -d --build
podman-compose pull
podman-compose down
podman-compose logs -f <service>
podman-compose up -d <service>
```

---

## 🔟 Environment Files (`.env`)

- Compose auto-loads `.env` **only in the same directory as docker-compose.yml**
    
- For multiple env files:
    

```yaml
services:
  gitea:
    env_file:
      - .env
      - ../../configs/shared.env
```

- Or manually via CLI:
    

```bash
docker compose --env-file myvars.env up -d
```

- Best practice:
    
    - **Service-specific `.env`** in each service folder
        
    - **Shared `.env`** in `configs/`
        
    - Explicitly reference both in Compose
        

---

## 1️⃣1️⃣ Updating a Container / Service

### Full workflow (safe for multi-service Compose)

```bash
# 1. Pull latest images
docker compose pull
# or for one service
docker compose pull gitea

# 2. Stop old containers
docker compose down

# 3. Recreate & start
docker compose up -d
# or rebuild images if build: used
docker compose up -d --build
```

### Minimal downtime (update one service only)

```bash
docker compose pull gitea
docker compose up -d gitea
```

### Podman Compose equivalent

```bash
podman-compose pull
podman-compose down
podman-compose up -d
podman-compose up -d gitea
```

> Volumes persist automatically; data is safe.

---

## 1️⃣2️⃣ Useful One-Liners

|Action|Docker|Podman|
|---|---|---|
|Show disk usage|`docker system df`|`podman system df`|
|Show container env|`docker exec <c> env`|`podman exec <c> env`|
|Copy file container → host|`docker cp <c>:/path/file .`|`podman cp <c>:/path/file .`|
|Copy file host → container|`docker cp ./file <c>:/path/`|`podman cp ./file <c>:/path/`|

---

## ✅ Summary

- **Docker / Podman**: basic container management, volumes, images
- **Compose / Podman Compose**: multi-service orchestration
- **.env**: local only unless explicitly referenced
- **Update workflow**: `pull` → `down` → `up -d`
- **Single service update**: `pull <service>` → `up -d <service>`

This cheatsheet covers almost everything you need to **run, debug, and update containers in your home-lab** safely and efficiently.
