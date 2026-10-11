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

<table>
  <tr>
    <td width="50%" align="center">
      <img src="https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/nano-editor.png" alt="Writing the file in nano" width="100%"><br>
      <em>Figure 1. Writing <code>docker-compose.yml</code> in the nano editor.</em>
    </td>
    <td width="50%" align="center">
      <img src="https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/compose-file.png" alt="docker-compose.yml printed in the terminal" width="100%"><br>
      <em>Figure 2. Output of <code>cat docker-compose.yml</code> showing the saved file with correct indentation.</em>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <img src="https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/compose-deployment.png" alt="Deployment and running containers" width="100%"><br>
      <em>Figure 3. Output of <code>docker-compose up -d</code> and <code>docker-compose ps</code> showing both containers running.</em>
    </td>
    <td width="50%" align="center">
      <img src="https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/nextcloud-web.png" alt="Nextcloud setup page" width="100%"><br>
      <em>Figure 4. Nextcloud setup page reached through port 8080.</em>
    </td>
  </tr>
  <tr>
    <td colspan="2" align="center">
      <img src="https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/compose-teardown.png" alt="Teardown" width="50%"><br>
      <em>Figure 5. Output of <code>docker-compose down</code> showing the containers and network being removed.</em>
    </td>
  </tr>
</table>

<br>

## 🛠️ Skills Learned

- Learned how to describe a whole multi-container app in one `docker-compose.yml` file instead of typing long commands, and got comfortable writing space-sensitive YAML in `nano` even though one wrong indent breaks everything.
- Deployed and shut down a full stack using `docker-compose up -d` and `docker-compose down`, which honestly felt like a magic trick the first time it worked.
- Figured out how containers find each other by service name, like how Nextcloud knew to look for `database` because of the `MYSQL_HOST` variable, and used environment variables to configure containers without hardcoding anything.
- Learned to only expose the web tier on port `8080` while keeping the database hidden inside the network, which is a pretty smart security move that I didn't appreciate before.
- Got better at verifying deployments with `docker-compose ps`, opening the app in a browser to confirm it worked, and writing clear documentation in Markdown organized in GitHub, which is something real engineers do every day.

<br>

## 📁 Repository Content

| File | Description |
| :--- | :--- |
| [README.md](README.md) | Overview of the mission, commands, and skills learned |
| [multi-tier-architecture.md](multi-tier-architecture.md) | Research on the two-tier architecture used in this lab |
| [docker-compose-guide.md](docker-compose-guide.md) | Technical documentation of the `docker-compose.yml` file |
| [reflection.md](reflection.md) | Personal reflection on the mission |
| [screenshots/](screenshots/) | Evidence of the deployment, web access, and teardown |

