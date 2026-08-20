# Infrastructure Report

This report covers the technical specs of the Linux server used in the
KillerCoda Playground for CloudNova Technologies' cloud infrastructure
assessment.

### Linux Distribution
    Description:    Ubuntu 24.04.4 LTS

### Kernel Version
    6.8.0-138-generic

### CPU Model
    Model name:    Intel Xeon E312xx (Sandy Bridge, IBRS update)

### Number of CPU
    CPU(s):    1

### Total RAM

| | Total | Used | Free | Shared | Buff/Cache | Available |
|---|---|---|---|---|---|---|
| Mem | 1.9Gi | 426Mi | 846Mi | 1.1Mi | 798Mi | 1.4Gi |
| Swap | 1.0Gi | 0B | 1.0Gi | — | — | — |

### Disk Capacity

| Filesystem | Size | Used | Avail | Use% | Mounted on |
|---|---|---|---|---|---|
| tmpfs | 191M | 996K | 190M | 1% | /run |
| /dev/vda1 | 19G | 5.4G | 13G | 30% | / |
| tmpfs | 952M | 84K | 952M | 1% | /dev/shm |
| tmpfs | 5.0M | 0 | 5.0M | 0% | /run/lock |
| /dev/vda16 | 881M | 117M | 703M | 15% | /boot |
| /dev/vda15 | 105M | 6.2M | 99M | 6% | /boot/efi |

### Mounted File Systems

| Filesystem | Type | Size | Used | Avail | Use% | Mounted on |
|---|---|---|---|---|---|---|
| tmpfs | tmpfs | 191M | 996K | 190M | 1% | /run |
| /dev/vda1 | ext4 | 19G | 5.4G | 13G | 30% | / |
| tmpfs | tmpfs | 952M | 84K | 952M | 1% | /dev/shm |
| tmpfs | tmpfs | 5.0M | 0 | 5.0M | 0% | /run/lock |
| /dev/vda16 | ext4 | 881M | 117M | 703M | 15% | /boot |
| /dev/vda15 | vfat | 105M | 6.2M | 99M | 6% | /boot/efi |

### Hostname
    ubuntu

### IP Address
    172.30.1.2   172.17.0.1


## Commands Used

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
