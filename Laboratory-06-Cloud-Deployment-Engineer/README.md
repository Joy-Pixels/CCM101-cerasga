# Laboratory 6: The Cloud Deployment Engineer

<br>

## 🎯 Mission Overview

Congratulations! Your flawless work in deploying data storage solutions has earned you a spot on the Cloud Deployment Team at CloudNova Technologies.

Up until now, you have been deploying single containers (like a standalone web server or a storage bucket). However, real-world enterprise applications are rarely just one container. They are "multi-tier" systems that require a frontend web application communicating seamlessly with a backend database. Deploying these one by one manually is prone to error.

Enter Docker Compose. In this mission, you will transition from manual commands to Infrastructure as Code (IaC). Using a YAML configuration file, you will define a multi-container private cloud storage application (Nextcloud and MariaDB) and deploy the entire stack simultaneously with a single command!

> Remember: A junior engineer deploys servers by typing commands; a senior engineer deploys infrastructure by writing code.

<br>

## 📋 Objectives

At the end of this laboratory activity, you should be able to:

- Explain the concept of a multi-tier application architecture.
- Understand the purpose and structure of a docker-compose.yml file.
- Use a Linux command-line text editor (nano) to create configuration files.
- Deploy a multi-container application (Nextcloud + Database) using Docker Compose.
- Document deployment procedures and Infrastructure as Code (IaC) principles using Markdown.
- Continue expanding your professional GitHub Cloud Computing Portfolio.

<br>

## 💻 Commands Executed

| Command | Purpose |
| :--- | :--- |
| `mkdir nextcloud-deployment` | Created a project directory |
| `cd nextcloud-deployment` | Moved into the project directory |
| `nano docker-compose.yml` | Created the Compose file in the nano editor |
| `cat docker-compose.yml` | Verified the file saved with correct indentation |
| `docker-compose up -d` | Pulled the images and started both containers in the background |
| `docker-compose ps` | Confirmed both containers were running |
| `docker-compose down` | Stopped and removed the containers and the network |

<br>

## 🛠️ Skills Learned

- Describing a multi-container application as code in a `docker-compose.yml` file.
- Writing space-sensitive YAML using a terminal text editor (`nano`).
- Deploying and tearing down a full stack with `docker-compose up -d` and `docker-compose down`.
- Connecting containers by service name (`MYSQL_HOST=database`) through the automatic Compose network.
- Configuring containers with environment variables.
- Publishing only the web tier (port 8080) while keeping the database internal.
- Verifying a deployment with `docker-compose ps` and by accessing the app through a browser.
- Documenting infrastructure and evidence in Markdown and organizing it in a GitHub repository.

<br>

## 📁 Repository Content

| File | Description |
| :--- | :--- |
| [README.md](README.md) | Overview of the mission, commands, and skills learned |
| [multi-tier-architecture.md](multi-tier-architecture.md) | Research on the two-tier architecture used in this lab |
| [docker-compose-guide.md](docker-compose-guide.md) | Technical documentation of the `docker-compose.yml` file |
| [reflection.md](reflection.md) | Personal reflection on the mission |
| [screenshots/](screenshots/) | Evidence of the deployment, web access, and teardown |

