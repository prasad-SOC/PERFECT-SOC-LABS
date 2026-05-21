# Linux Lab 4 — Log Analysis

## Lab Overview

In this lab, we explore how Linux systems store and manage logs.  
Log analysis is one of the most important skills for SOC analysts, system administrators, and cybersecurity professionals because logs contain evidence of system activity, authentication attempts, errors, and potential security incidents.

This lab focuses on viewing, filtering, and analyzing Linux log files using common command-line tools.

---

# Lab Objectives

By completing this lab, you will learn how to:

- Understand the purpose of Linux log files
- Navigate important log directories
- Read system logs using terminal commands
- Filter logs using keywords
- Monitor authentication-related events
- Search for failed login attempts
- Analyze logs efficiently using command-line tools

---

# Lab Environment

| Component | Details |
|---|---|
| Operating System | Ubuntu Linux |
| Tools Used | cat, less, tail, grep, journalctl |
| Privileges Required | Standard User / sudo for some logs |

---

# Important Linux Log Locations

| Log File | Purpose |
|---|---|
| `/var/log/syslog` | General system activity logs |
| `/var/log/auth.log` | Authentication and login logs |
| `/var/log/kern.log` | Kernel-related logs |
| `/var/log/dmesg` | Boot and hardware logs |
| `/var/log/apache2/` | Apache web server logs |
| `/var/log/apt/` | Package installation logs |

---

# Step 1 — Navigate to the Log Directory

Open the terminal and move into the log directory:

```bash
cd /var/log
````

List available log files:

```bash
ls
```

---

# Step 2 — View System Logs

Display the contents of the system log:

```bash
cat syslog
```

Since logs can be very large, use `less` for easier navigation:

```bash
less syslog
```

Controls inside `less`:

* Press `Space` → Next page
* Press `b` → Previous page
* Press `q` → Quit

---

# Step 3 — Monitor Live Logs

Use `tail` to view the latest log entries:

```bash
tail syslog
```

Monitor logs in real time:

```bash
tail -f syslog
```

This is useful for live monitoring and incident detection.

Press:

```bash
CTRL + C
```

to stop monitoring.

---

# Step 4 — Analyze Authentication Logs

Authentication logs are extremely important in security monitoring.

View authentication events:

```bash
sudo less /var/log/auth.log
```

Common activities found here:

* User logins
* Failed login attempts
* sudo command usage
* SSH authentication events

---

# Step 5 — Search Logs Using grep

Search for failed login attempts:

```bash
grep "Failed password" /var/log/auth.log
```

Search for sudo activity:

```bash
grep "sudo" /var/log/auth.log
```

Search for SSH events:

```bash
grep "ssh" /var/log/auth.log
```

---

# Step 6 — Use journalctl

Modern Linux systems use `systemd` logging.

View recent logs:

```bash
journalctl
```

Show recent boot logs:

```bash
journalctl -b
```

View SSH-related logs:

```bash
journalctl | grep ssh
```

Show logs in real time:

```bash
journalctl -f
```

---

# Step 7 — Investigate Suspicious Activity

Look for indicators such as:

* Multiple failed logins
* Unknown users
* Repeated sudo attempts
* Unusual SSH access
* System errors

Example:

```bash
grep "Failed password" /var/log/auth.log
```

If repeated failures appear from the same IP, it may indicate a brute-force attempt.

---

# Key SOC Analyst Takeaways

* Logs are critical evidence sources during investigations
* Authentication logs help detect unauthorized access attempts
* Real-time monitoring helps identify incidents quickly
* Filtering logs reduces noise and improves analysis speed
* Linux logging is foundational for blue team operations

---

# Commands Used

```bash
cd /var/log
ls
cat syslog
less syslog
tail syslog
tail -f syslog
grep "Failed password" /var/log/auth.log
grep "sudo" /var/log/auth.log
journalctl
journalctl -b
journalctl -f
```

```
```
