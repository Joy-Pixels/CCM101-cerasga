# Cloud Infrastructure Components

This document identifies the core cloud infrastructure components observed
in the KillerCoda Linux environment, based on the concepts discussed in
Chapter 2 (Cloud Infrastructure, Cloud Technologies, and Professional
Development).

---

## 1. Compute Resources

| Aspect | Description |
|---|---|
| Purpose | This is basically the "brain" of the server, it's what actually does the processing and runs everything. Without compute, nothing would execute. |
| Importance in Cloud Computing | Compute is one of the basic building blocks of any cloud setup. What's useful about cloud compute is that more processing power can be added in minutes instead of buying and installing new hardware, which is a huge advantage for companies. |
| Relation to KillerCoda | The KillerCoda VM was found to have only 1 vCPU (an Intel Xeon E312xx, Sandy Bridge), as shown using `lscpu`. It is a small-scale example of the same kind of virtual machine setup that cloud providers use, just scaled down since it is a free sandbox environment. Below is the image showing the output of the `lscpu` command in the KillerCoda terminal. |

<p align="center">
<img src="https://github.com/Joy-Pixels/Portfolio/blob/95f2d4c2cd0290e77f5d44f447f4c408a1fec226/compute-resources.png" alt="CPU information from lscpu command" width="600"/>
<br>
<sub><i>Figure 1: CPU information retrieved using the `lscpu` command.</i></sub>
</p>

---

## 2. Storage Resources

| Aspect | Description |
|---|---|
| Purpose | This is where all the actual files live — the OS, apps, and any data are saved here so nothing disappears when the server restarts. |
| Importance in Cloud Computing | Cloud storage lets companies add more space whenever needed without buying physical drives. Providers also spread storage across multiple systems so data does not disappear if one disk fails. |
| Relation to KillerCoda | The server's main disk was identified as `/dev/vda1`, a 19G ext4 partition mounted at `/`, as shown using `df -h`. This is essentially block storage attached to a VM, similar to what AWS EBS or Azure Managed Disks provide for real cloud servers. Below is the image showing the output of the `df -h` command in the KillerCoda terminal. |

<p align="center">
<img src="https://github.com/Joy-Pixels/Portfolio/blob/95f2d4c2cd0290e77f5d44f447f4c408a1fec226/storage-resources.png" alt="Disk usage from df -h command" width="600"/>
<br>
<sub><i>Figure 2: Disk usage and capacity retrieved using the `df -h` command.</i></sub>
</p>

---

## 3. Networking Resources

| Aspect | Description |
|---|---|
| Purpose | Networking is what lets the server communicate with other computers, whether that's other servers or a user's browser connecting to it. |
| Importance in Cloud Computing | Networking ties compute and storage together and connects everything to the internet. Cloud networking also includes tools like firewalls and load balancers that keep traffic secure and properly managed. |
| Relation to KillerCoda | Running `hostname -I` showed the server has two IPs, `172.30.1.2` and `172.17.0.1`. The second is likely a Docker bridge network. This is a small-scale version of how real cloud setups use virtual networks, such as AWS VPCs or Azure VNets, to organize and separate traffic. Below is the image showing the output of the `hostname -I` command in the KillerCoda terminal. |

<p align="center">
<img src="https://github.com/Joy-Pixels/Portfolio/blob/95f2d4c2cd0290e77f5d44f447f4c408a1fec226/networking-resources.png" alt="IP address output from hostname -I command" width="600"/>
<br>
<sub><i>Figure 3: IP address information retrieved using the `hostname -I` command.</i></sub>
</p>

---

## 4. Operating System

| Aspect | Description |
|---|---|
| Purpose | The OS is the software that manages everything else on the machine, such as memory, files, and running programs. It is the layer between the hardware and the applications. |
| Importance in Cloud Computing | Linux is the dominant OS for cloud servers, which is why Linux skills are highly valued for cloud engineers. Most cloud provider VM images across AWS, Azure, and GCP run on Linux distributions like Ubuntu. |
| Relation to KillerCoda | The server runs Ubuntu 24.04.4 LTS on kernel `6.8.0-138-generic`, confirmed with `lsb_release -d` and `uname -r`. Working in this Ubuntu environment provides hands-on practice with the same type of OS used to manage real cloud servers. Below is the image showing the output of the `lsb_release -d` and `uname -r` commands in the KillerCoda terminal. |

<p align="center">
<img src="https://github.com/Joy-Pixels/Portfolio/blob/95f2d4c2cd0290e77f5d44f447f4c408a1fec226/operating-system.png" alt="OS and kernel version from lsb_release and uname commands" width="600"/>
<br>
<sub><i>Figure 4: OS and kernel version retrieved using the `lsb_release -d` and `uname -r` commands.</i></sub>
</p>
