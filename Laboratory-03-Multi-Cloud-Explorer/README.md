<div align="center">

# Linux Investigation

</div>

<p align="justify">
This section documents the system information gathered from a Linux server running on a KillerCoda Playground, along with an analysis of which AWS, Azure, and GCP services could host this server if it were migrated to the cloud.
</p>

---

## 🎯 Mission Objectives

<p align="justify">
At the end of this laboratory activity, you should be able to:
</p>

- Explore the major public cloud platforms.
- Identify the core services offered by AWS, Microsoft Azure, and Google Cloud Platform.
- Compare cloud services across different providers.
- Analyze business requirements and recommend appropriate cloud solutions.
- Create professional technical documentation using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

---

## 🖥️ System Information

### Operating System
     Linux ubuntu 6.8.0-138-generic #138-Ubuntu SMP PREEMPT_DYNAMIC Fri Jul 31 22:41:49 UTC 2026 x86_64 x86_64 x86_64 GNU/Linux
    
### CPU Model

| Field | Value |
|---|---|
| Architecture | x86_64 |
| CPU op-mode(s) | 32-bit, 64-bit |
| Address sizes | 39 bits physical, 48 bits virtual |
| Byte Order | Little Endian |
| CPU(s) | 1 |
| On-line CPU(s) list | 0 |
| Vendor ID | GenuineIntel |
| BIOS Vendor ID | Red Hat |
| Model name | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| BIOS Model name | RHEL-9.6.0 PC (Q35 + ICH9, 2009) CPU @ 2.0GHz |
| BIOS CPU family | 1 |
| CPU family | 6 |
| Model | 42 |
| Thread(s) per core | 1 |
| Core(s) per socket | 1 |
| Socket(s) | 1 |
| Stepping | 1 |
| BogoMIPS | 7008.00 |
| Flags | fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 syscall nx rdtscp lm constant_tsc rep_good nopl xtopology cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx hypervisor lahf_lm cpuid_fault pti ssbd ibrs ibpb stibp tsc_adjust xsaveopt arat md_clear |
| Hypervisor vendor | KVM |
| Virtualization type | full |
| L1d cache | 32 KiB (1 instance) |
| L1i cache | 32 KiB (1 instance) |
| L2 cache | 4 MiB (1 instance) |
| L3 cache | 16 MiB (1 instance) |
| NUMA node(s) | 1 |
| NUMA node0 CPU(s) | 0 |

**Vulnerabilities:**

| Vulnerability | Status |
|---|---|
| Gather data sampling | Not affected |
| Indirect target selection | Mitigation; Aligned branch/return thunks |
| Itlb multihit | KVM: Mitigation: VMX unsupported |
| L1tf | Mitigation; PTE Inversion |
| Mds | Mitigation; Clear CPU buffers; SMT Host state unknown |
| Meltdown | Mitigation; PTI |
| Mmio stale data | Unknown: No mitigations |
| Reg file data sampling | Not affected |
| Retbleed | Not affected |
| Spec rstack overflow | Not affected |
| Spec store bypass | Mitigation; Speculative Store Bypass disabled via prctl |
| Spectre v1 | Mitigation; usercopy/swapgs barriers and __user pointer sanitization |
| Spectre v2 | Mitigation; Retpolines; IBPB conditional; IBRS_FW; STIBP disabled; RSB filling; PBRSB-eIBRS Not affected; BHI Retpoline |
| Srbds | Not affected |
| Tsa | Not affected |
| Tsx async abort | Not affected |
| Vmscape | Not affected |

### Memory

| | Total | Used | Free | Shared | Buff/Cache | Available |
|---|---|---|---|---|---|---|
| Mem | 1.9Gi | 429Mi | 850Mi | 1.1Mi | 790Mi | 1.4Gi |
| Swap | 1.0Gi | 0B | 1.0Gi | — | — | — |

### Disk Space

| Filesystem | Size | Used | Avail | Use% | Mounted on |
|---|---|---|---|---|---|
| tmpfs | 191M | 996K | 190M | 1% | /run |
| /dev/vda1 | 19G | 5.4G | 13G | 30% | / |
| tmpfs | 952M | 84K | 952M | 1% | /dev/shm |
| tmpfs | 5.0M | 0 | 5.0M | 0% | /run/lock |
| /dev/vda16 | 881M | 117M | 703M | 15% | /boot |
| /dev/vda15 | 105M | 6.2M | 99M | 6% | /boot/efi |

---

## ⌨️ Commands Used

- `uname -a` – displays the operating system, hostname, and kernel version
- `lscpu` – displays CPU architecture and specifications
- `free -h` – displays memory usage in human-readable format
- `df -h` – displays disk space usage in human-readable format

---

**Terminal session showing the Linux Commands Executed using KillerCoda Playground:**

<div align="center">

<table>
<tr>
<td align="center">
<img src="https://github.com/Joy-Pixels/CCM101-cerasga/blob/2ce2446c89488766b6737f36967965887cd749ba/Laboratory-03-Multi-Cloud-Explorer/screenshots/checkpoint-7.1.png" width="500"><br>
</td>
<td align="center">
<img src="https://github.com/Joy-Pixels/CCM101-cerasga/blob/2ce2446c89488766b6737f36967965887cd749ba/Laboratory-03-Multi-Cloud-Explorer/screenshots/checkpoint-7.2.png" width="500"><br>
</td>
</tr>
</table>

</div>

---

## ☁️ Cloud Migration Analysis

<p align="justify">
If this Linux server were moved to the cloud, it could be hosted using Amazon EC2 on AWS, Azure Virtual Machines on Azure, or Compute Engine on GCP. All three services let you create virtual machines that match the same operating system, CPU, memory, and disk space as this KillerCoda server, in this case, Ubuntu with 1 vCPU, about 2 GB of RAM, and 19 GB of disk space. You just pick an instance size (or "machine type") that matches or exceeds what this Linux server currently uses, install the same OS, and the app or workload can run the same way, just now in the cloud instead of on a physical or local machine.
</p>

<div align="center">

| Provider | Equivalent Service | Suggested Instance Type |
|---|---|---|
| AWS | Amazon EC2 | t3.micro |
| Azure | Azure Virtual Machines | B1s |
| GCP | Compute Engine | e2-micro |

</div>
