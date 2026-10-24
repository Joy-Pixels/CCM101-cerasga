# Checkpoint 2 - Automation Research 

This document explains the core concepts of Linux automation that were applied during Mission 9. Understanding these tools is essential before writing scripts and configuring schedulers to automate cloud operations.

<br>

## 1. Bash Script

A Bash script is essentially a text file filled with a list of commands meant to be carried out by the Linux system all at once. The very first line, `#!/bin/bash`, works much like a set of instructions on a recipe card telling you which chef should follow it; in this case, it tells the computer to use the Bash interpreter to understand the code.

<div align="center">
  <img src="https://github.com/Joy-Pixels/Portfolio/blob/a96764116307a9c951f0ec05eb8f0df3f73997ee/Lab%209/bash_script.png" alt="Bash Script" width="500">
</div>

<div align="center">
  <em>Figure 1: A code snippet of the <code>backup.sh</code> script showing the shebang line, variables, and backup commands.</em>
</div>

<br>

## 2. Variables

Programmers rely on variables, such as `$BACKUP_DIR`, to hold data in a temporary storage spot so the exact same folder path doesn't have to be typed out repeatedly. This functions like a labeled storage box where you put something important and just read the label later, making the code much easier to read and allowing you to update the path in one single place if it ever changes.

<div align="center">
  <img src="https://github.com/Joy-Pixels/Portfolio/blob/49a755d46c28209e8f05317fd94f2ecb00c59c6c/Lab%209/backup.png" alt="Variables in programming" width="500">
</div>

<div align="center">
  <em>Figure 2: A terminal snippet demonstrating the <code>$BACKUP_DIR</code> variable being used within the <code>mkdir</code> command to create a directory.</em>
</div>

<br>

## 3. Cron Job

A cron job is a scheduled task in Linux that automatically runs a script or command at specific times or intervals. It is essential for cloud operations because it completely removes the need for human intervention, ensuring that critical repetitive tasks like backups happen consistently without anyone pushing a button. Similarly, this works just like a programmable thermostat that turns on the heat at a set time every morning, guaranteeing the house is warm without anyone having to remember to flip a switch.

<div align="center">
  <img src="https://cyberin.in/blog/wp-content/uploads/2025/12/Flowchart-63.png" alt="Cron job diagram" width="400">
</div>

<div align="center">
  <em>Figure 3: A flowchart illustrating the automated scheduling and triggering process of a cron job.</em>
</div>

<br>
<br>

## References
- Cyberin. (2025). *Cron job flowchart* [Image]. Retrieved from https://cyberin.in/blog/wp-content/uploads/2025/12/Flowchart-63.png
