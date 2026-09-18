# Laboratory Activity 4 — Mission 4: The Cloud-Native Engineer

## Mission Overview

After successfully guiding clients through multi-cloud evaluations, I was promoted to the Cloud-Native Engineering Team at CloudNova Technologies. Modern cloud computing is no longer just about renting Virtual Machines (VMs) from AWS or Azure. Today's enterprise applications are built using lightweight, portable, and lightning-fast technologies called **containers**.

In this mission, I stepped into the shoes of a Cloud-Native Engineer using the **KillerCoda Playground**. I researched the differences between VMs and containers, executed my first Docker commands, and deployed a live, containerized web server (Nginx) in seconds.

> **Key lesson:** A traditional system administrator manages servers, but a cloud-native engineer manages the services running on them.

---

## Objectives

At the end of this laboratory activity, I was able to:

- Differentiate between traditional Virtual Machines (VMs) and Containers.
- Access a Docker-enabled cloud environment using KillerCoda.
- Execute fundamental Docker CLI (Command Line Interface) commands.
- Pull, run, manage, and terminate a containerized application (Nginx).
- Create professional technical documentation of container operations using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

---

## 1. Docker Commands Executed

Below is every command I ran in Checkpoints 3, 4, and 5.

### Checkpoint 3 — Verify Docker Installation

| Command | Purpose |
|---------|---------|
| `docker --version` | Shows the installed Docker version. |
| `docker info` | Displays full details about the Docker environment (containers, images, storage driver, kernel version, etc.). |

**Output observed:**
- Docker version **29.1.3**
- Operating System: Ubuntu 24.04.4 LTS
- Containers: 0, Images: 0 (fresh environment)

**Screenshot:** 

---

### Checkpoint 4 — Deploy Your First Container (Nginx)

| Command | Purpose |
|---------|---------|
| `docker pull nginx` | Downloads the official Nginx image from Docker Hub. |
| `docker run -d -p 8080:80 --name my-nginx nginx` | Runs the Nginx container in the background (detached mode) and maps port 8080 on the host to port 80 inside the container. |
| `curl http://localhost:8080` | Sends an HTTP request to verify the web server is running and returns the "Welcome to nginx!" page. |

**Output observed:** The full HTML of the Nginx welcome page was returned, confirming the containerized web server was live.

**Screenshot:** 

---

### Checkpoint 5 — The Container Lifecycle

| # | Command | What It Did |
|---|---------|-------------|
| 1 | `docker ps` | Listed all running containers, showing `my-nginx` was **Up**. |
| 2 | `docker stop my-nginx` | Gracefully stopped the running container named `my-nginx`. |
| 3 | `docker ps -a` | Listed all containers, including stopped ones, confirming `my-nginx` had **Exited (0)**. |
| 4 | `docker rm my-nginx` | Completely deleted the stopped container from the system. |
| 5 | `docker ps -a` | Confirmed the container list was now empty. |

**Screenshot:** 

---

