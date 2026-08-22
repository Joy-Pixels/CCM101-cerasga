# 🚀 Laboratory Activity 2: Build the Cloud Infrastructure Blueprint

## 📋 Mission Overview

Congratulations,

Your onboarding has been successfully completed, and your Cloud Computing Portfolio has been approved by your supervisor.

CloudNova Technologies has now assigned you to your **first official project**.

Before deploying cloud services, every cloud engineer must understand the infrastructure that powers modern cloud computing. Your mission is to investigate the components of cloud infrastructure, identify how compute, storage, networking, and identity services work together, and document your findings as if you were preparing technical documentation for a client.

Using the **KillerCoda Playground**, Linux tools, official cloud documentation, and your GitHub Cloud Computing Portfolio, you will complete a series of engineering tasks that simulate the planning phase of a cloud deployment.

Remember: **Great cloud engineers build systems—but exceptional cloud engineers document and justify every design decision.**

<br>

## 🎯 Objectives

At the end of this laboratory activity, you should be able to:

- Explain the major components of cloud infrastructure.
- Investigate the hardware and software resources available in a Linux environment.
- Differentiate compute, storage, networking, and identity resources.
- Interpret the relationship between cloud infrastructure components.
- Create professional technical documentation using Markdown.
- Continue building a structured GitHub Cloud Computing Portfolio.

<br>

## 🧩 Cloud Infrastructure Components

<table>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/blob/2d6cc8ebb20ab0e8b5044e234b99918962aa2e7f/cloud-removebg-preview.png" width="50"></h1></td>
<td>

**1. Compute Resources**

The processing power of the server. It's what actually runs the operating system and any applications on top of it. For example, Amazon EC2, Microsoft Azure Virtual Machines, Google Compute Engine, and even physical servers or personal computers (CPUs like Intel Xeon, AMD EPYC) are all forms of compute resources.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/blob/2d6cc8ebb20ab0e8b5044e234b99918962aa2e7f/Database-removebg-preview.png" width="50"></h1></td>
<td>

**2. Storage Resources**

Where files and data are kept, like the disk partitions on the server. This is what keeps information saved even after the server restarts. For example, Amazon S3, Azure Blob Storage, and Google Cloud Storage are common cloud storage services used to store files and data.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/blob/6108072a0d02fbe3bd455a396ac7a220f480c48e/Internet.png" width="50"></h1></td>
<td>

**3. Networking Resources**

What allows the server to connect and communicate with other systems, users, or the internet. For example, Amazon VPC, Azure Virtual Network, and Google Virtual Private Cloud are used to manage networking and connectivity in the cloud.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/blob/2d6cc8ebb20ab0e8b5044e234b99918962aa2e7f/Linux-removebg-preview.png" width="50"></h1></td>
<td>

**4. Operating System**

The software layer that manages the server's hardware and lets everything else (files, processes, users) run properly. In this case, it's Ubuntu Linux. For example, Ubuntu, Red Hat Enterprise Linux, and Windows Server are common operating systems used to run cloud servers.

</td>
</tr>
</table>

<br>

## 🛠️ Tools Used

<table>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/blob/f1fc74ab84404cb8fb0ff9f5ec7d3980476a9457/killercoda.png" width="50"></h1></td>
<td>

**KillerCoda:**
KillerCoda is a free, browser-based interactive learning platform that
provides temporary Linux sandbox environments for practicing DevOps,
Kubernetes, and cloud-related skills without needing to install
anything locally. It was used to access a live Linux server and run
commands to investigate its system information.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/blob/f1fc74ab84404cb8fb0ff9f5ec7d3980476a9457/LucidChart.png" width="50"></h1></td>
<td>

**Lucidchart:**
Lucidchart is a web-based diagramming tool used to create flowcharts,
network diagrams, and infrastructure diagrams through a simple
drag-and-drop interface. It was used to design and build the cloud
infrastructure diagram for Checkpoint 5.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/blob/f1fc74ab84404cb8fb0ff9f5ec7d3980476a9457/Claude.jpg" width="50"></h1></td>
<td>

**Claude:**
Claude is an AI assistant developed by Anthropic that can help with
tasks like research, writing, and technical documentation. It was
used for generating ideas and getting guidance while working through
the laboratory tasks.

</td>
</tr>
</table>

<br>

## 💻 Linux Commands Executed

| Command | What It Is | How It Was Used |
|---|---|---|
| `lsb_release -d` | **LSB** stands for Linux Standard Base, a specification that defines a common structure for Linux distributions. `lsb_release` is a utility that reads distribution info (from `/etc/lsb-release` or `/etc/os-release`) and prints it in a standardized way. The `-d` flag shows only the "Description" line. | Used to confirm the exact OS name and version, Ubuntu 24.04.4 LTS. Note: the system reported "No LSB modules are available," meaning the full LSB compatibility package isn't installed, but the description still worked since it fell back to distro release files. |
| `uname -r` | `uname` (short for "Unix name") prints system information about the OS and kernel. The `-r` flag specifically shows the **kernel release**, the exact build/version of the Linux kernel running the machine. | Used to identify the kernel version, 6.8.0-138-generic, which tells us the Linux kernel build and confirms this is a "generic" Ubuntu kernel (not a custom/cloud-optimized variant). |
| `lscpu \| grep "Model name"` | `lscpu` ("list CPU") displays detailed CPU architecture info gathered from `/proc/cpuinfo` and other system files, including model, cores, threads, cache, and virtualization support. Piping to `grep "Model name"` filters the long output down to just the CPU model line. | Used to identify the physical/virtual CPU model, Intel Xeon E312xx (Sandy Bridge), which tells us this VM is emulating an older server-class Xeon processor commonly used in virtualization/cloud hosts. |
| `lscpu \| grep "^CPU(s):"` | Same `lscpu` tool, filtered (using `^` to match the start of the line) to the "CPU(s):" line, which reports the total number of logical processors (cores × threads) available to the OS. | Used to confirm this server has only 1 CPU core, typical of a resource-limited sandbox/playground environment. |
| `free -h` | `free` reports memory usage, RAM and swap, by reading `/proc/meminfo`. The `-h` flag ("human-readable") converts raw byte counts into readable units like MiB/GiB instead of long numbers. | Used to capture total, used, and available RAM (1.9Gi total) and swap (1.0Gi total, unused), giving a snapshot of memory pressure on the server. |
| `df -h` | `df` stands for "disk free." It reports available and used disk space for all mounted filesystems. `-h` again makes the sizes human-readable. | Used to see how much disk space each partition (like `/dev/vda1`) has used versus available, and which mount point each belongs to. |
| `df -hT` | Same `df` command as above, with the added `-T` flag to display each filesystem's **type** (e.g., ext4, vfat, tmpfs) alongside its usage stats. | Used to identify not just disk usage but the filesystem type behind each mount point, needed to distinguish real disk partitions (ext4/vfat) from virtual memory-backed filesystems (tmpfs). |
| `hostname` | `hostname` simply prints (or sets) the system's configured network hostname, the name used to identify the machine on a network. | Used to record the server's hostname, ubuntu. |
| `hostname -I` | Same `hostname` command, with the `-I` (capital i) flag, which lists all IP addresses currently assigned to the machine's network interfaces, rather than just the hostname. | Used to capture the server's IP addresses, 172.30.1.2 (primary interface) and 172.17.0.1 (likely a Docker/container bridge interface). |

<p align="center">
  <sub><i>Figure 1: Terminal session showing the Linux Commands Executed using KillerCoda Playground</i></sub>
  <br>
  <br>
  <img src="https://github.com/Joy-Pixels/Portfolio/blob/ba2e61b47dfc83d7a781e8d374fbfe10e659a1d3/System_Infrastructure.png" alt="System Infrastructure" width="600"/>
</p>

<br>

## 📚 Skills Learned

- Learned additional Linux command lines for identifying system
  information.
- Gained an in-depth understanding of how a system works together
  with the cloud.
- Practiced creating a cloud infrastructure blueprint, which may be
  helpful in future projects.
- Learned about the different cloud providers and how their services
  compare to one another.

<br>

## ⚠️ Challenges Encountered

One of the main challenges was experiencing information overload,
since there was a lot of new material to take in, including new
Linux commands, cloud infrastructure concepts, and the differences
between cloud providers, all within a short period of time. It took
some patience and repetition to fully process everything, but
breaking the tasks down checkpoint by checkpoint made it more
manageable.
