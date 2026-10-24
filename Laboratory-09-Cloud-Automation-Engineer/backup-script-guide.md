# Checkpoint 6 - Backup Script Guide

This document is a technical guide for the client's IT team at CloudNova Technologies. It explains how the automated backup script was created, how it was made executable, and how it is scheduled to run every night at 2:00 AM without anyone pressing a button.

<br>

## 📋 A. Procedure

### Step 1: Create the Application Data

```bash
cd ~
mkdir app-data
echo "This is critical client data." > app-data/data.txt
cat app-data/data.txt
```

Expected output: `This is critical client data.`

### Step 2: Create the Bash Script

```bash
nano backup.sh
```

Type or paste the script from Part B (Full Code of `backup.sh`) into the editor.

### Step 3: Save and Exit nano

Press **Ctrl + O**, then **Enter**, then **Ctrl + X**. Confirm the script saved correctly:

```bash
cat backup.sh
```

<p align="center">
  <img src="screenshots/checkpoint%203%20-%20script-creation.png" alt="Script creation" width="400">
  <br>
  <sub><b>Figure 1:</b> Creating the data folder and saving backup.sh in nano</sub>
</p>

### Step 4: Try to Run the Script (Permission Error)

```bash
./backup.sh
```

Result: `bash: ./backup.sh: Permission denied`

### Step 5: Make the Script Executable

```bash
chmod +x backup.sh
```

### Step 6: Run the Script

```bash
./backup.sh
```

Expected output:

```
Initiating automated backup...
Backup completed successfully at 20261023_161639!
```

### Step 7: Verify the Backup

```bash
ls -l backups/
```

A file named like `backup_20261023_161639.tar.gz` should be listed.

### Step 8: Schedule the Backup with Cron

```bash
crontab -l
env EDITOR=nano crontab -e
```

Add this line at the bottom of the file, then save and exit nano:

```
0 2 * * * /root/backup.sh
```

### Step 9: Verify the Schedule

```bash
crontab -l
```

The last line of the output should be `0 2 * * * /root/backup.sh`.

---
<br>

## 📘 B. Required Technical Documentation

### 1. Full Code of `backup.sh`

The script defines the source folder and backup folder, creates the backup folder if it does not exist, and compresses the source data into a timestamped `.tar.gz` file.

```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p $BACKUP_DIR

# Compress the source directory into a tarball (.tar.gz)
tar -czf $BACKUP_DIR/backup_$TIMESTAMP.tar.gz $SOURCE_DIR

echo "Backup completed successfully at $TIMESTAMP!"
```

**What each part does:**

| Line | Purpose |
| :--- | :--- |
| `#!/bin/bash` | The shebang. It tells Linux to run the file using the Bash shell. |
| `SOURCE_DIR="app-data"` | Stores the folder to back up in a variable. |
| `BACKUP_DIR="backups"` | Stores the folder where backups are saved. |
| `TIMESTAMP=$(date +"%Y%m%d_%H%M%S")` | Saves the current date and time so each backup file has a unique name. |
| `mkdir -p $BACKUP_DIR` | Creates the backup folder. The `-p` flag prevents an error if it already exists. |
| `tar -czf ...` | Compresses the source folder into a `.tar.gz` file (`c` = create, `z` = gzip compress, `f` = file name). |
| `echo ...` | Prints status messages at the start and end of the backup. |

> #### Script Execution

<p align="center">
  <img src="screenshots/checkpoint%204%20-%20script-execution.png" alt="Script execution" width="400">
  <br>
  <sub><b>Figure 2:</b> Permission denied, chmod +x, successful run, and the .tar.gz file in backups/</sub>
</p>

<br>

### 2. What the `chmod +x` Command Did

By default, Linux protects users from running text files as programs. A newly created `backup.sh` has only read and write permissions, so the first `./backup.sh` attempt returned a "Permission denied" error.

The command `chmod +x backup.sh` changed the file's permissions. `chmod` stands for "change mode," and `+x` adds the **execute** permission. This tells Linux the file is allowed to run as a program. After this change, the permissions went from `-rw-r--r--` (no execute) to `-rwxr-xr-x` (execute allowed), and the script ran successfully.

<br>

### 3. Cron Expression and Time-Field Breakdown

The following cron expression was added to the crontab to run the backup automatically:

```
0 2 * * * /root/backup.sh
```

| Position | Field | Value Used | Meaning |
| :--- | :--- | :--- | :--- |
| 1 | **Minute** | `0` | Run at minute 0, exactly on the hour. |
| 2 | **Hour** | `2` | Run at 2:00 AM (24-hour clock). |
| 3 | **Day of Month** | `*` | Run on every day of the month. |
| 4 | **Month** | `*` | Run in every month of the year. |
| 5 | **Day of Week** | `*` | Run on every day of the week (Sunday through Saturday). |
| | **Command** | `/root/backup.sh` | The full path of the script to execute. |

**Conclusion:** This expression runs `/root/backup.sh` at exactly 2:00 AM every day.

> #### Cron Installation Output

<p align="center">
  <img src="screenshots/checkpoint%205%20-%20cron-schedule.png" alt="Cron schedule" width="400">
  <br>
  <sub><b>Figure 3:</b> Installed crontab showing 0 2 * * * /root/backup.sh</sub>
</p>

---
<br>

## ⚠️ C. Notes to Consider

While the automation is working, the IT team must remember a few critical rules to make sure the system is actually reliable. Here are the 7 most important takeaways.

**1. File Paths Must Be Exact.** The cron job is instructed to look for the script at `/root/backup.sh`. If an administrator accidentally moves the file to a different folder, the automated backup will fail silently. It is best practice to use absolute paths so the computer always knows exactly where to look.

**2. Watch Out for Timezones.** Many cloud servers use UTC time by default, which might be different from the client's local time. If the timezone is not checked, the server's "2:00 AM" could happen during busy business hours and slow down the network.

**3. Cron Jobs Run Silently.** Because cron jobs run in the background, they do not show error messages on the screen if something goes wrong. The IT team should add logging (like `>> /root/backup.log 2>&1`) to keep a written record of each backup, which makes errors much easier to troubleshoot.

**4. Hard Drives Will Fill Up.** The script creates a new compressed file every night but never deletes the old ones. Without a retention policy (a rule to delete backups older than 30 days), the server's disk will eventually run out of space.

**5. Keep Backups in a Separate Location.** Right now, the backups are saved on the same server as the original data. If the server crashes or gets hacked, both the data and the backup are lost. A reliable strategy copies the files to external storage, such as a separate cloud server.

**6. Typos in Automation Are Dangerous.** Because cron runs the script automatically every night, a typo in the code will also run every night, with no one watching. For example, if a typo changes a delete command, it could wipe out data on thousands of servers at once. Scripts must be tested carefully, and only trusted administrators should be allowed to edit them.

**7. This Lab Environment Is Temporary.** The KillerCoda playground is a temporary practice space. The server will reset, so the cron job will not actually fire at 2:00 AM. The goal of this lab is to show that the schedule can be installed and verified with `crontab -l`.
