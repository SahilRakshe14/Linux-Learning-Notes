
<div align="center">

# 🐧 LINUX COMMAND HANDBOOK

### A Complete Practical Linux Command Reference

**Ubuntu | Linux Administration | DevOps | Development**

![Linux](https://img.shields.io/badge/OS-Linux-orange?logo=linux)
![Ubuntu](https://img.shields.io/badge/Platform-Ubuntu-E95420?logo=ubuntu&logoColor=white)
![Learning](https://img.shields.io/badge/Learning-In%20Progress-blue)
![Commands](https://img.shields.io/badge/Commands-100%2B-success)

*My personal Linux learning notes, practical commands, examples and explanations.*

</div>

---

## 📌 About This Repository

This repository contains my personal Linux command reference, created while learning Linux and Ubuntu.

It covers essential commands used in Linux administration, file management, user management, system monitoring, process management, networking, automation and DevOps workflows.

**Learning Source:** [Linux Tutorial for Beginners – YouTube](https://youtu.be/ldgl9Bd3lLg)

**Purpose:**
- Understand Linux commands and their practical usage.
- Maintain a quick reference for future revision.
- Develop hands-on Linux administration skills.
- Build a strong foundation for Python, Backend Development and DevOps.

---

# 📚 Table of Contents

1. System Information & Environment
2. Hardware & Resource Monitoring
3. File Navigation & Reading
4. User & Group Administration
5. Package Management (APT)
6. Permissions & Ownership
7. Process & Service Management
8. Environment Variables & PATH
9. Archives & Compression
10. Cron Jobs & Scheduling
11. Networking & Remote File Transfer

---

# 1. System Information & Environment

Commands used to identify the Linux operating system, kernel, hostname and current user environment.

| Command | Description |
|---|---|
| `uname -s` | Displays the operating system kernel name. |
| `uname -a` | Displays complete system and kernel information. |
| `uname -r` | Displays the kernel release version. |
| `cat /etc/os-release` | Shows Linux distribution and version details. |
| `hostnamectl` | Displays or manages system hostname information. |
| `whoami` | Displays the current logged-in username. |
| `pwd` | Displays the current working directory. |
| `hostname` | Displays the system hostname. |

**Practical Examples**

```bash
uname -a
uname -r
cat /etc/os-release
hostnamectl
whoami
pwd
hostname
```

---

# 2. Hardware & Resource Monitoring

Commands used to monitor CPU, RAM, disk space, storage devices and system performance.

| Command | Description |
|---|---|
| `nproc` | Displays the number of available processing units. |
| `lscpu` | Displays CPU architecture, cores and processor details. |
| `free -h` | Displays RAM and swap memory usage in readable format. |
| `vmstat` | Displays memory, CPU, process and I/O statistics. |
| `df -h` | Displays available and used disk space. |
| `lsblk` | Lists storage devices and partitions. |
| `du -sh /home` | Displays total disk usage of the /home directory. |

**Practical Examples**

```bash
nproc
lscpu
free -h
vmstat
df -h
lsblk
du -sh /home
```

---

# 3. File Navigation & Reading

Commands used to navigate directories, create files and read file contents.

| Command | Description |
|---|---|
| `pwd` | Displays the current directory path. |
| `ls` | Lists files and directories. |
| `ls -la` | Displays all files, including hidden files, with details. |
| `cd ..` | Moves to the parent directory. |
| `cd ~` | Moves to the user's home directory. |
| `cd /` | Moves to the root directory. |
| `mkdir folder` | Creates a new directory. |
| `touch file.txt` | Creates an empty file. |
| `cat file.txt` | Displays the complete file content. |
| `cat -n file.txt` | Displays file content with line numbers. |
| `less file.txt` | Opens an interactive file viewer. |
| `cp file.txt backup.txt` | Copies a file. |
| `mv file.txt new.txt` | Moves or renames a file. |
| `rm file.txt` | Deletes a file. |
| `rmdir folder` | Removes an empty directory. |
| `./script.sh` | Executes a script from the current directory. |

**Practical Examples**

```bash
mkdir LinuxPractice
cd LinuxPractice
touch notes.txt
cat notes.txt
ls -la
pwd
cd ..
```

**Reading Files with less**

```bash
less notes.txt
```

Useful keys:
- `Space` – Next page.
- `b` – Previous page.
- `/word` – Search for a word.
- `q` – Exit.

**Executing a Shell Script**

```bash
chmod +x script.sh
./script.sh
```

---

# 4. User & Group Administration

Linux supports multiple users and groups. These commands help manage accounts and access permissions.

| Command | Description |
|---|---|
| `whoami` | Displays the current username. |
| `id` | Displays UID, GID and group information. |
| `sudo adduser john` | Creates a new user account. |
| `su - john` | Switches to another user with a login environment. |
| `sudo usermod -aG sudo john` | Adds a user to the sudo group. |
| `sudo passwd john` | Changes the user's password. |
| `groups john` | Displays the groups associated with a user. |
| `sudo userdel -r john` | Deletes a user and their home directory. |

**Practical Examples**

```bash
sudo adduser developer
id developer
groups developer
sudo passwd developer
```

**Switch User**

```bash
su - developer
```

**Give Sudo Access**

```bash
sudo usermod -aG sudo developer
```

**Important:** Log out and log in again for the new group membership to take effect in the user's sessions.

**Delete User**

```bash
sudo userdel -r developer
```

⚠️ This permanently deletes the user's home directory and associated data. Use carefully.

---

# 5. Package Management (APT)

APT stands for Advanced Package Tool. It manages software installation, updates and removal on Ubuntu.

| Command | Description |
|---|---|
| `sudo apt update` | Refreshes package lists. |
| `sudo apt upgrade` | Upgrades installed packages. |
| `sudo apt full-upgrade` | Performs upgrades while handling dependency changes. |
| `sudo apt install nginx` | Installs Nginx and its dependencies. |
| `sudo apt remove nginx` | Removes Nginx but keeps configuration files. |
| `sudo apt purge nginx` | Removes Nginx and its package configuration files. |
| `apt list --installed` | Lists installed packages. |
| `apt policy nginx` | Displays package versions and installation status. |
| `sudo apt autoremove` | Removes unnecessary dependency packages. |
| `sudo apt clean` | Clears downloaded package archive files. |

**Practical Examples**

```bash
sudo apt update
sudo apt upgrade
```

**Install Software**

```bash
sudo apt install nginx
```

**Check Package Information**

```bash
apt policy nginx
apt list --installed
```

**Remove Software**

```bash
sudo apt remove nginx
```

---

# 6. Permissions & Ownership

Linux permissions control who can read, write and execute files.

### Permission Types

| Permission | Symbol | Numeric Value |
|---|---|---|
| Read | r | 4 |
| Write | w | 2 |
| Execute | x | 1 |

### Permission Categories

- User (u) – File owner.
- Group (g) – Members of the assigned group.
- Others (o) – All other users.

### Important Commands

| Command | Description |
|---|---|
| `ls -l` | Displays file permissions and ownership. |
| `chmod +x script.sh` | Adds execute permission for all users. |
| `chmod 755 file` | Sets owner to rwx and group/others to r-x. |
| `chmod 644 file` | Sets owner to rw- and group/others to r--. |
| `sudo chown alice:developers app.py` | Changes file owner and group. |
| `sudo chgrp developers app.py` | Changes only the group ownership. |
| `sudo chown -R alice:developers project/` | Recursively changes directory ownership. |

**Understanding chmod 755**

```bash
chmod 755 script.sh
```

- Owner = 7 = Read + Write + Execute.
- Group = 5 = Read + Execute.
- Others = 5 = Read + Execute.

**Ownership Examples**

```bash
sudo chown alice:developers app.py
sudo chgrp developers app.py
ls -l app.py
```

**Recursive Ownership**

```bash
sudo chown -R alice:developers project/
```

⚠️ Avoid changing permissions or ownership recursively on system directories unless you understand the consequences.

---

# 7. Process & Service Management

Processes are running programs. Services are background processes managed by the system.

### Process Management

| Command | Description |
|---|---|
| `ps aux` | Displays running processes for all users. |
| `pgrep -a nginx` | Finds matching process IDs and command lines. |
| `top` | Monitors processes in real time. |
| `htop` | Provides an interactive process monitor. |
| `kill 1234` | Sends a graceful termination signal. |
| `kill -9 1234` | Forces immediate process termination. |
| `pkill nginx` | Terminates processes matching a name. |

**Practical Examples**

```bash
ps aux
top
pgrep -a nginx
```

To exit `top`, press `q`.

**Terminate a Process**

```bash
kill 1234
```

Use force termination only when normal termination fails:

```bash
kill -9 1234
```

### Service Management (Systemd)

| Command | Description |
|---|---|
| `systemctl status nginx` | Checks service status. |
| `sudo systemctl start nginx` | Starts a service. |
| `sudo systemctl stop nginx` | Stops a service. |
| `sudo systemctl restart nginx` | Restarts a service. |
| `sudo systemctl reload nginx` | Reloads service configuration if supported. |
| `sudo systemctl enable --now nginx` | Enables automatic startup and starts the service. |
| `journalctl -u nginx -n 50 -f` | Follows the latest 50 service log lines. |

**Practical Examples**

```bash
sudo systemctl status nginx
sudo systemctl start nginx
sudo systemctl enable nginx
```

**View Live Logs**

```bash
sudo journalctl -u nginx -n 50 -f
```

Press `Ctrl + C` to stop following logs.

---

# 8. Environment Variables, PATH & Shell Configuration

Environment variables store configuration values used by programs and shell sessions.

| Command | Description |
|---|---|
| `printenv` | Displays environment variables. |
| `export APP_ENV=production` | Creates an environment variable for child processes. |
| `echo $APP_ENV` | Displays the variable value. |
| `which ls` | Finds the executable location using PATH. |
| `type cd` | Identifies command type. |
| `echo $PATH` | Displays PATH directories. |
| `source ~/.bashrc` | Reloads the Bash configuration file. |

**Practical Examples**

```bash
printenv
echo $PATH
which ls
type cd
```

**Create Environment Variable**

```bash
export APP_ENV=production
echo $APP_ENV
```

**Reload Bash Configuration**

```bash
source ~/.bashrc
```

---

# 9. Archives & Compression

These commands help combine, compress and extract files and directories.

| Command | Description |
|---|---|
| `tar -cf project.tar project/` | Creates an uncompressed TAR archive. |
| `tar -tf project.tar` | Lists archive contents. |
| `tar -xf project.tar` | Extracts a TAR archive. |
| `gzip project.tar` | Compresses a file using gzip. |
| `gunzip project.tar.gz` | Decompresses a gzip file. |
| `tar -czf project.tar.gz project/` | Creates a compressed TAR archive. |
| `tar -xzf project.tar.gz` | Extracts a compressed TAR archive. |
| `zip -r project.zip project/` | Creates a ZIP archive recursively. |
| `unzip project.zip` | Extracts a ZIP archive. |

**Practical Examples**

```bash
tar -cf project.tar project/
tar -tf project.tar
tar -xf project.tar
```

**Create Compressed Archive**

```bash
tar -czf project.tar.gz project/
```

**Extract Compressed Archive**

```bash
tar -xzf project.tar.gz
```

**ZIP Compression**

```bash
zip -r project.zip project/
unzip project.zip
```

---

# 10. Cron Jobs & Scheduling

Cron is a Linux utility used to schedule commands and scripts automatically.

| Command | Description |
|---|---|
| `crontab -e` | Opens the current user's cron configuration. |
| `crontab -l` | Lists scheduled cron jobs. |
| `crontab -r` | Removes all cron jobs for the current user. |

### Cron Syntax

```text
* * * * * command
| | | | |
| | | | +--- Day of week
| | | +----- Month
| | +------- Day of month
| +--------- Hour
+----------- Minute
```

**Example:**

```bash
0 9 * * * /home/sanket/backup.sh
```

This schedules the script every day at 9:00 AM.

⚠️ `crontab -r` removes the entire user crontab. Use it carefully.

---

# 11. Networking & Remote File Transfer

Commands used to test network connectivity, configure web services and transfer files between machines.

### Network & Web Server Commands

| Command | Description |
|---|---|
| `curl http://127.0.0.1` | Sends an HTTP request to the local server. |
| `sudo nginx -t` | Tests Nginx configuration syntax. |
| `sudo ufw status` | Displays firewall status and rules. |

**Practical Examples**

```bash
curl http://127.0.0.1
sudo nginx -t
sudo ufw status
```

### Secure File Transfer (SCP)

| Command | Description |
|---|---|
| `scp page.html ubuntu@IP:/path/` | Copies a file to a remote server over SSH. |

**Example**

```bash
scp page.html ubuntu@192.168.1.10:/var/www/html/
```

### Rsync

| Command | Description |
|---|---|
| `rsync -av site/ ubuntu@IP:/path/` | Synchronizes files and directories with a remote server. |

**Example**

```bash
rsync -av site/ ubuntu@192.168.1.10:/var/www/site/
```

### SFTP

| Command | Description |
|---|---|
| `sftp ubuntu@IP` | Opens an interactive secure file transfer session. |

**Example**

```bash
sftp ubuntu@192.168.1.10
```

Useful SFTP commands:

```bash
ls
pwd
put file.txt
get file.txt
exit
```

**Note:** SCP, Rsync over SSH and SFTP require a reachable remote server with SSH access and valid authentication.

---

# ⭐ Important Linux Tips

1. Use `man command` to read the manual of a Linux command.
2. Use `command --help` to view command options.
3. Use `Tab` for command and filename autocomplete.
4. Use `history` to revisit previous commands.
5. Use `Ctrl + C` to stop a running foreground command.
6. Be careful with `sudo`, `rm -rf` and recursive permission commands.
7. Practice commands in a test directory before using them on important files.

**Example:**

```bash
man ls
ls --help
history
```

---

# 🎯 Learning Progress

- [ ] System Information & Environment
- [ ] Hardware & Resource Monitoring
- [ ] File Navigation & Reading
- [ ] User & Group Administration
- [ ] Package Management
- [ ] Permissions & Ownership
- [ ] Process & Service Management
- [ ] Environment Variables & PATH
- [ ] Archives & Compression
- [ ] Cron Jobs & Scheduling
- [ ] Networking & Remote File Transfer

---

# 🚀 Future Learning Topics

- [ ] Bash Scripting
- [ ] SSH Configuration
- [ ] Linux Networking Fundamentals
- [ ] Docker & Containers
- [ ] CI/CD Fundamentals
- [ ] Linux Server Administration
- [ ] Deployment & Cloud Basics

---

<div align="center">

**Learn • Practice • Document • Improve**

*Building strong Linux fundamentals, one command at a time.*

</div>
