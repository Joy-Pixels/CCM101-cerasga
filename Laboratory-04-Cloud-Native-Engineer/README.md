# Laboratory Activity 4 — Mission 4: The Cloud-Native Engineer

## 📖 Mission Overview

Congratulations! After successfully guiding our clients through multi-cloud evaluations, you have been 
promoted to the **Cloud-Native Engineering Team** at CloudNova Technologies. 

Modern cloud computing is no longer just about renting Virtual Machines (VMs) from AWS or Azure. Today's 
enterprise applications are built using lightweight, portable, and lightning-fast technologies called **Containers**. 
Your new mission is to understand the shift from traditional virtualization to containerization. 

Using the KillerCoda Playground, you will step into the shoes of a Cloud-Native Engineer. You will research the 
differences between VMs and containers, execute your very first Docker commands, and deploy a live, 
containerized web server in seconds. 

>  💡**Remember:** A traditional system administrator manages servers, but a cloud-native engineer manages the services running on them.

---
<br>

## 🎯 Objectives

At the end of this laboratory activity, I was able to:

- Differentiate between traditional Virtual Machines (VMs) and Containers.
- Access a Docker-enabled cloud environment using KillerCoda.
- Execute fundamental Docker CLI (Command Line Interface) commands.
- Pull, run, manage, and terminate a containerized application (Nginx).
- Create professional technical documentation of container operations using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

---
<br>

##  💻 Docker Commands Executed

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

| Screenshot 1 | Screenshot 2 |
|--------------|--------------|
| <img src="https://github.com/Joy-Pixels/CCM101-cerasga/blob/83a96cfea5d51e00bf89162f4919c0f598036e50/Laboratory-04-Cloud-Native-Engineer/screenshots/checkpoint-3.1_docker-version.png" alt="Checkpoint 3.1 — docker --version" width="400"/> | <img src="https://github.com/Joy-Pixels/CCM101-cerasga/blob/83a96cfea5d51e00bf89162f4919c0f598036e50/Laboratory-04-Cloud-Native-Engineer/screenshots/checkpoint-3.2_docker-version.png" alt="Checkpoint 3.2 — docker info" width="400"/> |

---

### Checkpoint 4 — Deploy Your First Container (Nginx)

| Command | Purpose |
|---------|---------|
| `docker pull nginx` | Downloads the official Nginx image from Docker Hub. |
| `docker run -d -p 8080:80 --name my-nginx nginx` | Runs the Nginx container in the background (detached mode) and maps port 8080 on the host to port 80 inside the container. |
| `curl http://localhost:8080` | Sends an HTTP request to verify the web server is running and returns the "Welcome to nginx!" page. |

**Output observed:** The full HTML of the Nginx welcome page was returned, confirming the containerized web server was live.

**Screenshot:** 

<img src="https://github.com/Joy-Pixels/CCM101-cerasga/blob/83a96cfea5d51e00bf89162f4919c0f598036e50/Laboratory-04-Cloud-Native-Engineer/screenshots/checkpoint-4_nginx-running.png" alt="Checkpoint 4 — Deploy Your First Container (Nginx)" width="600"/>

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

<img src="https://github.com/Joy-Pixels/CCM101-cerasga/blob/83a96cfea5d51e00bf89162f4919c0f598036e50/Laboratory-04-Cloud-Native-Engineer/screenshots/checkpoint-5_container-lifecycle.png" alt="Checkpoint 5 — The Container Lifecycle" width="600"/>

---

<br>

## 🧠 Skills Learned

Through this mission, I developed the following skills:

- **Understanding virtualization vs. containerization** — I can clearly explain how VMs and containers differ in architecture, boot time, resource usage, and isolation.
- **Using a cloud-based Docker environment** — I learned how to launch and work inside a KillerCoda Playground.
- **Running Docker CLI commands** — I can pull images, run containers, map ports, and inspect the Docker environment.
- **Managing the container lifecycle** — I can list, stop, verify, and remove containers confidently.
- **Deploying a web server in seconds** — I deployed a live Nginx web server using just a few commands, compared to 15+ minutes on a traditional VM.
- **Writing professional technical documentation** — I documented my work using Markdown and organized it into a GitHub portfolio.
- **Troubleshooting** — I learned why `http://localhost:8080` does not work from a local browser when the container runs on a remote cloud server, and how KillerCoda's "Traffic" port feature solves this.

---

<br>

## ⚠️ Challenges Encountered

During this mission, I faced a few challenges. At first, I had a hard time understanding the difference between Virtual Machines and Containers, so I read reliable sources and made a comparison table to see the differences clearly. I also got confused when I tried to open `http://localhost:8080` in my browser, because nothing appeared on the screen. I later learned that the container runs on a remote cloud server, not on my own laptop, so I used KillerCoda's **Traffic** feature to expose port 8080 and access the Nginx page successfully.

---

<br>

## 📚 References

Amazon Web Services. (2025, December 8). *Containers vs virtual machines: Understanding the difference*. AWS Builder Center. https://builder.aws.com/content/2lngiMeN3ZNKY4AFS5ih5lGVGN0/containers-vs-virtual-machines-understanding-the-difference

CleanStart. (2026, June 9). *Containers vs virtual machines: Architecture, security, and performance compared*. https://www.cleanstart.com/knowledge-hub/containers-vs-virtual-machines

Docker. (n.d.). *Docker documentation*. https://docs.docker.com/

KillerCoda. (n.d.). *KillerCoda playgrounds*. https://killercoda.com/playgrounds

