# Laboratory 7: The Cloud Operations Engineer

## 🎯 Mission Overview

Congratulations! Your ability to deploy multi-tier architectures has proven your technical capabilities. You have now been promoted to the Cloud Operations Team (often referred to in the industry as Site Reliability Engineering, or SRE) at CloudNova Technologies.

Deploying a cloud application is only the first step; keeping it running smoothly is the real challenge. When a server crashes or a web page takes ten seconds to load, you cannot simply guess what is wrong. You must rely on Observability and Monitoring to see inside your infrastructure.

Using the KillerCoda Playground, you will step into the role of a Cloud Operations Engineer. You will establish a performance baseline for your Linux server, deploy a containerized application, generate artificial web traffic, and hunt down performance metrics and system logs to prove the application is healthy.

> Remember: A developer hopes the application works; a Site Reliability Engineer uses metrics and logs to prove it.


<br>

## 📋 Objectives

At the end of this laboratory activity, you should be able to:

- Utilize native Linux command-line tools to monitor host CPU, Memory, and Disk capacity.
- Deploy a web container and track its real-time performance using Docker metrics.
- Generate web traffic and extract application access logs for analysis.
- Translate raw performance data into a readable technical report using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

<br>

## 💻 Monitoring Commands Executed

| Command | Purpose |
| :--- | :--- |
| `free -h` | Checked the host's total, used, and available memory (RAM) |
| `df -h /` | Checked the capacity and free space of the root file system |
| `top` | Viewed running processes, CPU load, and memory summary on the host |
| `docker run -d --name client-website -p 8080:80 nginx` | Deployed the Nginx web server in the background on port 8080 |
| `curl http://localhost:8080` | Simulated a normal user visit (run three times) |
| `curl http://localhost:8080/hidden-admin-page` | Simulated a request for a missing page to generate a 404 error |
| `docker logs client-website` | Retrieved the application logs showing the 200 and 404 requests |
| `docker stats` | Viewed the container's live CPU, memory, and network usage |

<br>

Below are the screenshots taken during the lab. They show the baseline checks on the Linux server, the deployment of the Nginx container, the traffic simulations (including the 404 error), and the live metrics.

<table>
  <tr>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 2 - memory-check.png" alt="Memory check" width="100%"><br>
      <em>Figure 1. Output of <code>free -h</code> showing host memory.</em>
    </td>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 2 - disk-check.png" alt="Disk check" width="100%"><br>
      <em>Figure 2. Output of <code>df -h /</code> showing root file system capacity.</em>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 2 - cpu-load-top.png" alt="Top command" width="100%"><br>
      <em>Figure 3. Output of <code>top</code> showing CPU load and processes.</em>
    </td>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 3 - install-nginx.png" alt="Nginx deployment" width="100%"><br>
      <em>Figure 4. Deploying the <code>client-website</code> Nginx container.</em>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 3 - simulation1.png" alt="Successful requests" width="100%"><br>
      <em>Figure 5. Three successful requests to the web server.</em>
    </td>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 3 - simulation2.png" alt="404 response" width="100%"><br>
      <em>Figure 6. Request for a missing page returning 404 Not Found.</em>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 4 - docker-logs.png" alt="Docker logs" width="100%"><br>
      <em>Figure 7. Output of <code>docker logs client-website</code> showing 200 and 404 entries.</em>
    </td>
    <td width="50%" align="center">
      <img src="screenshots/checkpoint 5 - container-metrics.png" alt="Docker stats" width="100%"><br>
      <em>Figure 8. Output of <code>docker stats</code> for the <code>client-website</code> container.</em>
    </td>
  </tr>
</table>

<br>

## 🛠️ Skills Learned

- **Checking Server Health:** Learned how to use basic Linux commands to quickly see how much RAM and disk space is left, and how to check the CPU using `top`.
- **Running Web Servers:** Figured out how to start a web server inside a Docker container and make it accessible on a specific port.
- **Testing with Fake Traffic:** Used the `curl` command to act like a real user visiting the site, and learned how to purposely break it by asking for a page that doesn't exist.
- **Reading Logs:** Discovered how to use `docker logs` to play detective and see exactly what requests the server received, including the successful ones and the errors.
- **Watching Live Metrics:** Used `docker stats` to see how much CPU and memory the container is actually using in real-time, which is super helpful for making sure it doesn't crash.
- **Writing Reports:** Practiced turning raw terminal text and screenshots into a clean, organized Markdown report for GitHub.

<br>

## 📁 Repository Content

| File | Description |
| :--- | :--- |
| [README.md](README.md) | Overview of the mission, commands, and skills learned |
| [system-baseline-report.md](system-baseline-report.md) | Host memory, disk, and CPU baseline |
| [container-observability.md](container-observability.md) | Nginx deployment, application logs, and container metrics |
| [reflection.md](reflection.md) | Personal reflection on the mission |
| [screenshots/](screenshots/) | Evidence of host checks, traffic simulation, logs, and metrics |
