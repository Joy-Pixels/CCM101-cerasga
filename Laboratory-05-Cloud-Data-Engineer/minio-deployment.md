# Checkpoint 5 - Technical Documentation

> This document records how I deployed an S3-compatible object storage server using Docker on a KillerCoda Ubuntu Playground, accessed its web console, and created a bucket for the client's photo-sharing app.

---

## A. Docker Command

This section shows the commands I used to download and start the MinIO server. The lab's original image (`minio/minio`) was not available, so I used the community fork `pgsty/minio`. I first confirmed that Docker and the network were working by pulling `hello-world` successfully, then tried `minio/minio` and `quay.io/minio/minio`, which both failed. The `pgsty/minio` fork pulled successfully, so I used it with the same ports, credentials, and arguments as the lab.

```bash
docker pull pgsty/minio

docker run -d -p 9000:9000 -p 9001:9001 --name minio-server -e "MINIO_ROOT_USER=cloudadmin" -e "MINIO_ROOT_PASSWORD=CloudNova2026!" pgsty/minio server /data --console-address ":9001"
```

Verified with:

```bash
docker ps
```

The `minio-server` container showed a status of "Up" with ports 9000-9001 mapped. Actual output is provided below.

<br>

<p align="center"><img src="https://github.com/Joy-Pixels/Portfolio/raw/059b07c549fd0bda91d3eb8e6834929dbf9d39c4/MinIO%20Deployed.png" alt="MinIO deployed" width="700"></p>

---

## B. Web Console Port

This section explains how I reached the MinIO management console from my browser. The server exposes two ports, and the console is the one used for administration.

| Item | Detail |
| :--- | :--- |
| **Console Port** | `9001` |
| **API Port** | `9000` (used by applications to talk to S3) |
| **Access Method** | KillerCoda **Traffic / Ports** tab → entered `9001` → clicked **Access** |

This opened the web console in a new browser tab, where I logged in with the credentials set in the Docker command. The fork's web console is branded "SILO," but it provides the same bucket creation and object browser features as the original MinIO. Actual output is provided below.

<br>

<p align="center"><img src="https://github.com/Joy-Pixels/Portfolio/raw/059b07c549fd0bda91d3eb8e6834929dbf9d39c4/MinIO%20Console%20Access.png" alt="MinIO console access" width="700"></p>

---

## C. Bucket Created

This section records the storage bucket I created for the client's photos and the test files I uploaded to prove that the system works.

| Item | Detail |
| :--- | :--- |
| **Bucket Name** | `client-photos` |
| **Access Level** | Private |
| **Test Files Uploaded** | `App Instructions.txt`, `Reflection.webp` |

Actual output is provided below.

<br>

<p align="center"><img src="https://github.com/Joy-Pixels/Portfolio/raw/059b07c549fd0bda91d3eb8e6834929dbf9d39c4/Bucket%20and%20uploaded%20files.png" alt="Bucket and uploaded files" width="700"></p>

---

## D. Environment Variables

This section explains the `-e` flags in the Docker command and what each one configured. The `-e` flag passes an environment variable into the container at startup, so the server can be configured without editing any files inside the container.

| Variable | Value | Purpose |
| :--- | :--- | :--- |
| `MINIO_ROOT_USER` | `cloudadmin` | Sets the username of the administrator (root) account used to log in to the console. |
| `MINIO_ROOT_PASSWORD` | `CloudNova2026!` | Sets the administrator's password. Without these two variables, MinIO would fall back to well-known default credentials, which is insecure. |

Putting a password directly in the command is fine for a lab, but in production it is risky because it can appear in shell history and in `docker inspect`. Real deployments use secrets management or environment files instead.
