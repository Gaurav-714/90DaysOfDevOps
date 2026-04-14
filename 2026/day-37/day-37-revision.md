# Day 37 – Docker Revision

## Self-Assessment

- [x] Run a container from Docker Hub (interactive + detached) — CAN DO
- [x] List, stop, remove containers and images — CAN DO
- [x] Explain image layers and caching — CAN DO
- [x] Write a Dockerfile — CAN DO
- [x] CMD vs ENTRYPOINT — SHAKY
- [x] Build and tag image — CAN DO
- [x] Named volumes — CAN DO
- [x] Bind mounts — CAN DO
- [x] Custom networks — CAN DO
- [x] Docker Compose multi-container — CAN DO
- [x] Environment variables in Compose — SHAKY
- [x] Multi-stage Dockerfile — SHAKY
- [x] Push image to Docker Hub — CAN DO
- [x] Healthchecks & depends_on — SHAKY

---

## Quick-Fire Answers

### 1. Image vs Container
- Image = blueprint (read-only)
- Container = running instance of that image

---

### 2. Data inside container on removal
- Lost permanently (unless using volumes or bind mounts)

---

### 3. Container communication (same network)
- Use container/service name as hostname
- Docker provides internal DNS

---

### 4. `docker compose down -v` vs `down`
- `down` → removes containers & networks
- `down -v` → ALSO removes volumes (data loss ⚠️)

---

### 5. Multi-stage builds
- Reduce image size
- Separate build environment from runtime
- Improve security & performance

---

### 6. COPY vs ADD
- COPY → simple file copy (preferred)
- ADD → can extract archives & fetch URLs

---

### 7. `-p 8080:80`
- Maps port 80 (container) → 8080 (host)

---

### 8. Check Docker disk usage
```bash
docker system df
```