# Linux Lab 3 — Process & Service Monitoring

## Objective
Learn how to monitor running processes, inspect system resource usage, and manage Linux services using common administrative commands.

---

# Lab Environment
- OS: Ubuntu Linux
- Terminal Access Required
- User Privileges: Standard User + sudo

---

# Tools & Commands Used
- ps
- top
- htop
- systemctl
- service
- kill
- pkill
- pidof

---

# What You Will Learn
In this lab, you will learn how to:

- View running processes
- Monitor CPU and memory usage
- Identify process IDs (PID)
- Stop unwanted processes
- Check active services
- Start and stop Linux services
- Understand basic process management

---

# Step 1 — View Running Processes

Display currently running processes:

```bash
ps
````

View detailed process information:

```bash
ps aux
```

### Explanation

* `a` → Shows processes from all users
* `u` → Displays user-oriented format
* `x` → Includes background processes

---

# Step 2 — Monitor System Processes in Real Time

Run:

```bash
top
```

### Observation

You will see:

* CPU usage
* Memory usage
* Running tasks
* Active users
* Process IDs

Press:

```text
q
```

to quit.

---

# Step 3 — Use htop (Optional but Recommended)

Install htop:

```bash
sudo apt install htop
```

Run:

```bash
htop
```

### Why htop?

* Easier to read
* Colorful interface
* Interactive process management

Exit using:

```text
F10
```

---

# Step 4 — Find a Process ID (PID)

Example:

```bash
pidof firefox
```

OR

```bash
ps aux | grep firefox
```

### Purpose

This helps identify the Process ID required for monitoring or terminating applications.

---

# Step 5 — Kill a Process

Terminate a process using PID:

```bash
kill PID
```

Example:

```bash
kill 2451
```

Forcefully terminate a process:

```bash
kill -9 PID
```

---

# Step 6 — Kill Processes by Name

Example:

```bash
pkill firefox
```

### Explanation

`pkill` stops processes directly using the process name.

---

# Step 7 — Check Running Services

View service status:

```bash
systemctl status ssh
```

Example output shows:

* Service state
* Active status
* Logs
* Process information

---

# Step 8 — Start and Stop Services

Start a service:

```bash
sudo systemctl start apache2
```

Stop a service:

```bash
sudo systemctl stop apache2
```

Restart a service:

```bash
sudo systemctl restart apache2
```

---

# Step 9 — Enable Services at Boot

Enable automatic startup:

```bash
sudo systemctl enable apache2
```

Disable startup:

```bash
sudo systemctl disable apache2
```

---

# SOC Analyst Relevance

Process and service monitoring is important in cybersecurity because analysts often investigate:

* Suspicious processes
* Malware execution
* Resource abuse
* Unauthorized services
* Persistence mechanisms
* Crypto miners
* Backdoors

Understanding Linux process management helps SOC analysts identify malicious behavior quickly.

---

# Key Takeaways

* `ps` displays running processes
* `top` monitors live system activity
* `kill` terminates unwanted processes
* `systemctl` manages services
* Process monitoring is essential for Linux administration and security operations

---

# Conclusion

In this lab, you explored Linux process and service monitoring fundamentals. You learned how to inspect active processes, monitor system resources, terminate processes, and manage Linux services using administrative commands commonly used by SOC analysts and system administrators.

Mastering these basics is essential before moving into advanced Linux security monitoring and incident investigation.

---

```
```
