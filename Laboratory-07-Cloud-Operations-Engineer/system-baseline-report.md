# System Baseline Report

## 1. Memory (RAM) Usage

To check the server's current memory usage, I ran the `free -h` command. This shows the total available RAM, how much is currently used, and how much is available for new processes.

![Memory Check Screenshot](screenshots/memory-check.png)

**Results:**
- **Total RAM available on the server:** 1.9 GiB
- **Available RAM:** 1.5 GiB
- **Used RAM:** 402 MiB

---

## 2. Disk Storage Capacity

To check the server's available disk storage, I ran the `df -h /` command. This shows the total size, used space, and available space on the root filesystem.

![Disk Check Screenshot](screenshots/disk-check.png)

**Results:**
- **Total Storage capacity of the root (/) file system:** 19 GiB
- **Used Storage:** 5.5 GiB
- **Available Storage:** 13 GiB
- **Use Percentage:** 30%

---

## 3. Active Running Processes and CPU Load

To view the active running processes and observe the CPU load, I opened the task manager by running the `top` command. I waited 5 seconds to observe the shifting CPU metrics, then pressed `q` to exit.

![Top Command Screenshot](screenshots/top-check.png)

**Observations:**
- **Total Tasks:** 128 total (1 running, 127 sleeping)
- **CPU Usage:** 0.0% user, 0.0% system, 100.0% idle
- **Load Average:** 0.00, 0.00, 0.00

---

<br>

## ✅ Why Checking Disk Space is Critical Before a Traffic Surge

Checking disk space is critical before a massive traffic surge because logs, container images, temporary files, and cached data can quickly fill the disk, causing the web server to slow down, crash, or fail to write new data entirely.

---

## Summary Table

| Resource | Total Capacity | Used | Available |
|---|---|---|---|
| RAM | 1.9 GiB | 402 MiB | 1.5 GiB |
| Disk (/) | 19 GiB | 5.5 GiB | 13 GiB |
| CPU Load | — | — | 0.00 average |


