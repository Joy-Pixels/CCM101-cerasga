# Laboratory Activity 9 - The Cloud Automation Engineer

## 🎯 Mission Overview

Congratulations! Your ability to secure cloud environments has proven you are ready for the highest level of operations. You have been promoted to the **Cloud Automation and DevOps Team** at CloudNova Technologies.

Up until now, you have been acting as a traditional systems administrator—typing commands manually one by one. In large enterprise environments scaling to thousands of servers, manual administration is too slow and highly prone to human error. To survive at scale, you must learn to automate.

Using the KillerCoda Playground, you will step into the role of a Cloud Automation Engineer. You will learn the basics of Bash shell scripting, create an automated backup routine, assign executable permissions, and configure the Linux Cron scheduler to run your code autonomously.

> #### Remember: If you have to do a task more than twice in the cloud, you should automate it.

## 📌 Objectives

At the end of this laboratory activity, you should be able to:

- Understand the fundamental syntax of a Bash shell script, including variables and basic commands.
- Use a command-line text editor (nano) to write and save executable scripts.
- Modify Linux file permissions using the chmod command.
- Understand task scheduling and the syntax of a Linux crontab.
- Document automation code and Cron job configurations using Markdown.
- Complete the final chapter of your GitHub Cloud Computing Portfolio.

## 💻 Commands Executed

| Command | Purpose |
| :--- | :--- |
| `mkdir app-data` | Created the dummy application directory |
| `echo "This is critical client data." > app-data/data.txt` | Created a test file to represent the client's data |
| `cat app-data/data.txt` | Verified the test file's contents |
| `nano backup.sh` | Opened the nano editor to write the backup script |
| `cat backup.sh` | Verified the script was saved correctly |
| `./backup.sh` | Tried to run the script (first failed with "Permission denied", then succeeded) |
| `chmod +x backup.sh` | Granted execute permission to the script |
| `ls -l backups/` | Verified the compressed `.tar.gz` backup was created |
| `crontab -l` | Listed the current cron jobs (before and after editing) |
| `env EDITOR=nano crontab -e` | Opened the crontab editor using nano |
| `0 2 * * * /root/backup.sh` | Cron entry added to run the backup every night at 2:00 AM |

## 🧰 Skills Learned

1. I learned how automated backups work in Linux and why compressing critical data is essential for preventing permanent data loss caused by human error.

2. I learned that file permissions are crucial for system security, and using `chmod +x` safely grants a script the right to execute like a real program.

3. I learned how to configure a cron job, which acts like a digital alarm clock that automatically schedules the backup script to run every night at 2:00 AM without manual help.

4. I learned how to write a basic Bash script using a shebang, variables, and command substitution to group multiple terminal commands into one single executable file.

5. I learned how to use the `tar` command to compress directories into timestamped `.tar.gz` archives, ensuring every backup file has a unique name and old data remains safe.

## 📸 Screenshots

<p align="center">
  <img src="screenshots/checkpoint%204%20-%20script-execution.png" alt="Script execution" width="450">
  <br>
  <sub><b>Figure 1:</b> Successful script execution and the .tar.gz file in backups/</sub>
</p>

<p align="center">
  <img src="screenshots/checkpoint%205%20-%20cron-schedule.png" alt="Cron schedule" width="450">
  <br>
  <sub><b>Figure 2:</b> Installed crontab showing 0 2 * * * /root/backup.sh</sub>
</p>

## 📁 Repository Content

| File | Description |
| :--- | :--- |
| [README.md](README.md) | Overview of the mission, commands, and skills learned |
| [automation-research.md](automation-research.md) | Definitions of Bash script, variables, and cron job |
| [backup-script-guide.md](backup-script-guide.md) | Step-by-step guide, full script, `chmod +x` explanation, and cron breakdown |
| [reflection.md](reflection.md) | Personal reflection on the mission |
| [screenshots/](screenshots/) | Evidence of script execution and cron schedule |
