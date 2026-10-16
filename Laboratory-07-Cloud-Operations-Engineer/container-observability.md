# Container Observability Report

This report documents the deployment of the client's Nginx web server (`client-website`) and the observability data I collected from it. It includes the commands used to generate test traffic, the application logs showing successful (200) and failed (404) requests, and the real-time CPU and memory metrics from `docker stats`, to check that the container is healthy before the marketing campaign traffic surge.

---

## 1. Deploying the Web Container and Generating Traffic

I deployed the client's Nginx web server in the background as `client-website`, mapped to port 8080, then sent test requests with `curl`.

```bash
docker run -d --name client-website -p 8080:80 nginx
```

This command downloads the official Nginx image if it is not already on the server and starts it as a container: `-d` runs it in the background, `--name client-website` gives it a fixed name, and `-p 8080:80` maps port 8080 on the host to port 80 inside the container.

<p align="center">
  <img src="screenshots/install-nginx.png" alt="Nginx container deployment" width="600">
  <br>
  <em>Figure 1. Deploying the <code>client-website</code> Nginx container on port 8080.</em>
</p>

**Three normal visits:**

```bash
curl http://localhost:8080
```

The `curl` command sends an HTTP request from the terminal, acting like a user visiting the website, and prints the response (the Nginx welcome page). I ran it three times to simulate three successful visits.

<p align="center">
  <img src="screenshots/simulation1.png" alt="Three successful requests" width="600">
  <br>
  <em>Figure 2. Three successful HTTP requests returning the Nginx welcome page.</em>
</p>

**One failed visit:**

```bash
curl http://localhost:8080/hidden-admin-page
```

This sends a request for a page that does not exist on the server, which makes Nginx return a "404 Not Found" response and gives me an error to look for in the logs.

<p align="center">
  <img src="screenshots/simulation2.png" alt="404 Not Found response" width="600">
  <br>
  <em>Figure 3. Request for a page that does not exist, returning a 404 Not Found response.</em>
</p>

---

## 2. Application Logs

I retrieved the container's logs with:

```bash
docker logs client-website
```

The `docker logs` command prints everything the named container has written to its output, including Nginx's startup messages and a record of every request it received.

<p align="center">
  <img src="screenshots/docker-logs.png" alt="Docker logs output" width="700">
  <br>
  <em>Figure 4. Output of <code>docker logs client-website</code> showing three successful requests (200) and one failed request (404).</em>
</p>

The single log line that shows the 404 error:

```
172.17.0.1 - - [15/Oct/2026:14:22:37 +0000] "GET /hidden-admin-page HTTP/1.1" 404 153 "-" "curl/8.5.0" "-"
```

### Why application logs are vital for troubleshooting

Application logs record exactly what happened: which URL was requested, the status code returned, when it happened, and which client sent it. With this detail, an engineer can find the cause of a problem quickly instead of guessing.

---

## 3. Real-Time Container Metrics

I viewed the container's live resource usage with:

```bash
docker stats
```

The `docker stats` command shows a live, continuously updating dashboard of each running container's CPU percentage, memory usage, network I/O, and disk I/O, so I can see how much of the server's resources the container is consuming.

<p align="center">
  <img src="screenshots/container-metrics.png" alt="Docker stats output" width="700">
  <br>
  <em>Figure 5. Output of <code>docker stats</code> for the <code>client-website</code> container.</em>
</p>

| Metric | Value at time of screenshot |
| :--- | :--- |
| **CPU usage** | **0.00%** |
| **Memory usage** | **2.715MiB** / 1.859GiB (0.14%) |
| Network I/O | 3.77kB received / 5.29kB sent |
| Block I/O | 0B read / 12.3kB written |
| PIDs | 2 |

At the time of the screenshot, the container was using only 2.715MiB of memory and 0.00% CPU, so it is healthy under light load. This is a baseline with only four test requests, so it shows the container is efficient at idle, not how it will behave under thousands of simultaneous users.
