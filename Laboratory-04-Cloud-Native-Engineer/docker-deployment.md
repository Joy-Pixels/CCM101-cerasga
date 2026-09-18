# 🐳 Docker Container Lifecycle

This document covers the essential commands for managing the lifecycle of a running container from listing and stopping to verifying and removing it.

<br>

## Container Lifecycle Commands

### 1. List Running Containers

**Command:**

```bash
docker ps
```

**What it does:** Displays all currently running containers along with their container ID, image, command, creation time, status, ports, and name — confirming which containers are active before managing them.

**Terminal Output:**

<img src="" alt="Output of docker ps showing the running my-nginx container" width="600"/>

💡 **Tip:** Use `docker ps -a` to list **all** containers (running *and* stopped).

---

<br>

### 2. Stop the Running Container

**Command:**

```bash
docker stop my-nginx
```

**What it does:** Gracefully shuts down the specified running container by sending a `SIGTERM` signal, allowing the application inside to exit cleanly before the container halts.

**Terminal Output:**

```bash
root@ubuntu:~$ docker stop my-nginx
my-nginx
```

---

<br>

### 3. Verify It Is Stopped

**Command:**

```bash
docker ps -a
```

**What it does:** Lists all containers (running and stopped), confirming the target container no longer appears as "Up" and instead shows an **Exited (0)** status — proving it has been successfully stopped.

**Terminal Output:**

```bash
root@ubuntu:~$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                      PORTS     NAMES
7ff4436ff783   nginx     "/docker-entrypoint.…"   2 minutes ago   Exited (0) 10 seconds ago             my-nginx
```

💡 **Tip:** Running `docker ps` (without `-a`) would show **no containers**, since only stopped containers remain.

---

<br>

### 4. Remove the Container Completely

**Command:**

```bash
docker rm my-nginx
```

**What it does:** Permanently deletes the stopped container from the system, freeing up disk space and removing all its associated writable layers and metadata.

**Terminal Output:**

```bash
root@ubuntu:~$ docker rm my-nginx
my-nginx
root@ubuntu:~$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

The final `docker ps -a` returns an **empty list**, confirming the container has been fully removed from the system.

---

<br>

## 📝 Summary

| # | Command | Purpose | Result |
|---|---|---|---|
| 1 | `docker ps` | List running containers | `my-nginx` shown as **Up** |
| 2 | `docker stop my-nginx` | Gracefully stop the container | Container halted |
| 3 | `docker ps -a` | Verify the container is stopped | Status shows **Exited (0)** |
| 4 | `docker rm my-nginx` | Permanently remove the container | Container deleted, list is empty |

Managing the container lifecycle is a core skill for a Cloud-Native Engineer. These four commands — **list → stop → verify → remove** — form the foundation of day-to-day container operations.

