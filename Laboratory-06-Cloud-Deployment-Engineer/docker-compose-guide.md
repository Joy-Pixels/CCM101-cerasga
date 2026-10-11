# Checkpoint 6 - Technical Documentation: Docker Compose Guide

This guide explains the `docker-compose.yml` file I wrote to deploy a two-tier Nextcloud stack (Nextcloud + MariaDB).

---

## The Full `docker-compose.yml`

I created the file with the `nano` editor inside a `nextcloud-deployment` directory.

![Writing the file in nano](https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/nano-editor.png)

```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

I confirmed the file saved with the correct indentation by printing it with `cat`:

![docker-compose.yml printed in the terminal](https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/compose-file.png)

---

## 1. What does the `services:` block do?

The `services:` block lists every container that makes up the application. Each item under it defines one container. This file has two:

| Service | Image | Role |
| :--- | :--- | :--- |
| `database` | `mariadb:10.6` | Database tier. Stores user credentials and file metadata. |
| `app` | `nextcloud` | Web/application tier. Serves the interface on port 8080. |

Instead of typing two separate `docker run` commands, I describe both containers once and Compose starts them together.

---

## 2. How did the Nextcloud app container find the database container?

Through the `MYSQL_HOST=database` environment variable. The value `database` is the **service name** of the MariaDB container. Compose automatically creates a private network (my output showed `Creating network "nextcloud-deployment_default"` before the containers were created), and Docker's internal DNS resolves each service name to its container. No IP addresses were needed.

The `database` service has no `ports:` entry, so it is only reachable inside that network. Only the `app` service is published to the outside on port 8080. The "Autoconfig file detected" banner below shows Nextcloud picked up the `MYSQL_*` variables from my Compose file.

![Nextcloud setup page](https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/nextcloud-web.png)

---

## 3. What is the difference between `docker run` and `docker-compose up -d`?

| Aspect | `docker run` | `docker-compose up -d` |
| :--- | :--- | :--- |
| **Scope** | One container per command. | All services in the YAML file. |
| **Networking** | Created and linked manually. | Created automatically. |
| **Repeatability** | Typed each time; easy to mistype. | The YAML file is reusable and can be versioned in Git. |
| **Teardown** | Stop and remove each container separately. | `docker-compose down` removes containers and network together. |

`docker run` is like building furniture piece by piece, while `docker-compose up -d` builds the whole set from one file. This is Infrastructure as Code: the setup is written in a file instead of typed from memory. The `-d` flag runs the stack in the background (detached mode) so the terminal stays free.

---

## Verification

`docker-compose ps` showed both containers `Up`. The app was published on `0.0.0.0:8080->80/tcp`, and the database showed only the internal `3306/tcp`.

![Deployment and running containers](https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/compose-deployment.png)

`docker-compose down` then stopped and removed both containers and the network.

![Teardown](https://github.com/Joy-Pixels/Portfolio/blob/16ae2dbc54dfa7c5064ec8e65b0b19fb53b579ca/compose-teardown.png)
