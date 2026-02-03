# Day 07 – Linux File System Hierarchy & Scenario-Based Practice (Beginner Friendly)

---

## Part 1: Linux File System Hierarchy

This section explains **where things are stored in Linux** in very simple words.

### / (root)

**What it is:** The main folder of Linux. Everything starts from here.

**Command used:**

```bash
ls -l /
```

**What I saw:** bin, etc, home, var

**I would use this when:** I want to see the full structure of the system.

---

### /home

**What it is:** Stores files of normal users.

**Command used:**

```bash
ls -l /home
```

**What I saw:** user folders

**I would use this when:** Checking user files, scripts, or documents.

---

### /root

**What it is:** Home folder of the root (admin) user.

**Command used:**

```bash
ls -l /root
```

**I would use this when:** Doing admin-level tasks.

---

### /etc

**What it is:** Contains configuration files.

**Command used:**

```bash
ls -l /etc
```

**What I saw:** hostname, hosts, ssh

**I would use this when:** Editing or checking service configuration.

---

### /var/log

**What it is:** Stores log files.

**Command used:**

```bash
ls -l /var/log
```

**What I saw:** syslog, auth.log

**I would use this when:** Finding errors and troubleshooting issues.

---

### /tmp

**What it is:** Temporary files.

**Command used:**

```bash
ls -l /tmp
```

**I would use this when:** Storing short-term files.

---

### Other Important Directories

### /bin

**What it is:** Basic Linux commands.

**Examples:** ls, cp, mv

**I would use this when:** Running basic commands.

---

### /usr/bin

**What it is:** User-installed commands.

**Examples:** git, python

**I would use this when:** Running programs.

---

### /opt

**What it is:** Third-party software.

**I would use this when:** Installing external tools.

---

### Hands-on Practice

**Find large log files:**

```bash
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

**Check hostname file:**

```bash
cat /etc/hostname
```

**Check home directory:**

```bash
ls -la ~
```

---

## Part 2: Scenario-Based Practice

### Scenario 1: Service Not Starting

**Step 1:**

```bash
systemctl status myapp
```

**Why:** Check if service failed or stopped.

**Step 2:**

```bash
journalctl -u myapp -n 50
```

**Why:** Check error messages.

**Step 3:**

```bash
systemctl is-enabled myapp
```

**Why:** Check if it starts on boot.

**Step 4:**

```bash
systemctl list-units --type=service | grep myapp
```

**Why:** Confirm service exists.

---

### Scenario 2: High CPU Usage

**Step 1:**

```bash
top
```

**Why:** See live CPU usage.

**Step 2:**

```bash
ps aux --sort=-%cpu | head -10
```

**Why:** Find high CPU process.

---

### Scenario 3: Finding Service Logs (Docker)

**Step 1:**

```bash
systemctl status docker
```

**Why:** Check service status.

**Step 2:**

```bash
journalctl -u docker -n 50
```

**Why:** View logs.

**Step 3:**

```bash
journalctl -u docker -f
```

**Why:** Follow logs live.

---

### Scenario 4: Permission Issue

**Step 1:**

```bash
ls -l /home/user/backup.sh
```

**Why:** Check permissions.

**Step 2:**

```bash
chmod +x /home/user/backup.sh
```

**Why:** Add execute permission.

**Step 3:**

```bash
./backup.sh
```

**Why:** Run the script.

---

## What I Learned Today

- Linux has fixed locations for files
- Logs are very important for troubleshooting
- Always check status → logs → permissions

---

### ✅ Day 07 Completed (Beginner Level)

#90DaysOfDevOps
#DevOpsKaJosh
#TrainWithShubham

Happy Learning
**TrainWithShubham**
---