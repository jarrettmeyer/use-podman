---
name: use-podman
description: Use podman when performing container operations on localhost.
---

# SKILL: use-podman

## Verify podman

Verify that the podman CLI is installed.

```bash
which podman
# => /opt/homebrew/bin/podman

podman --version
# => podman version 5.8.0
```

## Commands

### build

Build an image from a Containerfile/Dockerfile.

```bash
podman build --tag <image-name>:<tag> <context-path>

# Examples
podman build --tag myapp:latest .
podman build --tag myapp:v1.0 --file Containerfile.dev .
podman build --no-cache --tag myapp:latest .
```

### run

Run a container from an image.

```bash
podman run [OPTIONS] <image> [COMMAND]

# Examples
podman run --interactive --tty ubuntu:latest /bin/bash
podman run --detach --publish 8080:80 --name webserver nginx:latest
podman run --rm --volume $(pwd):/app myapp:latest
podman run --env DATABASE_URL=postgres://... myapp:latest
```

### logs

Fetch logs from a container.

```bash
podman logs [OPTIONS] <container>

# Examples
podman logs mycontainer
podman logs --follow mycontainer    # follow logs
podman logs --tail 100 mycontainer  # last 100 lines
```

### compose

Run multi-container applications.

```bash
podman compose up --detach
podman compose down
podman compose logs --follow
podman compose ps
```

### Container management

```bash
podman ps                    # list running containers
podman ps --all              # list all containers
podman stop <container>      # stop a container
podman rm <container>        # remove a container
podman images                # list images
podman rmi <image>           # remove an image
```

### Networking

```bash
podman network ls
podman network create <name>
podman network inspect <name>
podman network rm <name>
```

### Volumes

```bash
podman volume ls
podman volume create <name>
podman volume inspect <name>
podman volume rm <name>
```

## Key differences from Docker

- **Rootless by default**: Podman runs containers without root privileges
- **Daemonless**: No background daemon required; each command is a direct process
- **Docker-compatible CLI**: Most `docker` commands work with `podman`
- **Alias support**: You can alias `docker` to `podman` for compatibility
