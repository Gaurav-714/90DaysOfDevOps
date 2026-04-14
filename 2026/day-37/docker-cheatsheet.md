# Docker Cheat Sheet

## Container Commands

```bash
docker run -it ubuntu bash        # interactive container
docker run -d nginx               # detached mode
docker ps                         # list running containers
docker ps -a                      # list all containers
docker stop <id>                  # stop container
docker rm <id>                    # remove container
docker exec -it <id> bash         # access running container
docker logs <id>                  # view logs
```

---

## Image Commands

```bash
docker pull nginx                 # download image
docker build -t myapp .           # build image
docker images                     # list images
docker rmi <id>                   # remove image
docker tag myapp user/myapp       # tag image
docker push user/myapp            # push to Docker Hub
```

---

## Volume Commands

```bash
docker volume create myvol        # create volume
docker volume ls                  # list volumes
docker volume inspect myvol       # inspect volume
docker volume rm myvol            # remove volume
```

---

## Network Commands

```bash
docker network create mynet       # create network
docker network ls                 # list networks
docker network inspect mynet      # inspect network
docker network connect mynet c1   # connect container
```

---

## Docker Compose

```bash
docker compose up                # start services
docker compose up -d             # detached mode
docker compose down              # stop services
docker compose down -v           # remove volumes too
docker compose ps                # list services
docker compose logs              # logs
docker compose build             # build services
```

---

## Cleanup

```bash
docker system prune              # remove unused data
docker system prune -a           # remove all unused images
docker volume prune              # remove unused volumes
docker system df                 # disk usage
```

---

## Dockerfile Instructions

```bash
FROM python:3.11                # base image
WORKDIR /app                    # set working dir
COPY . .                        # copy files
RUN pip install -r req.txt      # install deps
EXPOSE 8000                     # expose port
CMD ["python", "app.py"]        # default command
ENTRYPOINT ["python"]           # fixed executable
```

---

## Useful Tips
- Use `.dockerignore` to reduce build size
- Prefer COPY over ADD
- Use multi-stage builds for smaller images
- Use named volumes for persistence
- Use custom networks for container communication