# 🛰️ Linux Lab 5 — Network Investigation

## 📌 Lab Overview
In this lab, we explored basic network investigation techniques in Linux.  
The goal was to understand how to inspect network connections, identify active services, analyze listening ports, and investigate remote communication from a Linux system.

Network investigation is an important skill for SOC analysts and cybersecurity professionals because attackers often communicate over the network after gaining access to a system.

---

# 🎯 Objectives

By completing this lab, you will learn how to:

- View network interface information
- Identify active network connections
- Detect listening services and ports
- Analyze remote IP communication
- Investigate suspicious network activity
- Understand basic network troubleshooting commands

---

# 🛠️ Tools & Commands Used

| Command | Purpose |
|---|---|
| `ip a` | View IP address and interfaces |
| `ifconfig` | Display network configuration |
| `ping` | Test connectivity |
| `netstat` | View network connections |
| `ss` | Display socket statistics |
| `curl` | Fetch data from URLs |
| `wget` | Download files from servers |
| `nslookup` | Query DNS information |
| `dig` | Advanced DNS lookup |
| `traceroute` | Trace packet path |
| `hostname -I` | Show system IP address |

---

# 🧪 Lab Setup

### Step 1 — View Network Interfaces

```bash
ip a
````

or

```bash
ifconfig
```

### Purpose

Displays:

* IP addresses
* MAC addresses
* Network interfaces
* Interface states

---

# 🔍 Step 2 — Check Internet Connectivity

```bash
ping google.com
```

### Purpose

Tests whether the system can communicate with external servers.

---

# 🌐 Step 3 — Display Active Connections

```bash
netstat -tunap
```

or

```bash
ss -tunap
```

### Purpose

Shows:

* Active TCP/UDP connections
* Listening ports
* Running services
* Process IDs associated with connections

---

# 🧭 Step 4 — Investigate DNS Information

```bash
nslookup google.com
```

or

```bash
dig google.com
```

### Purpose

Retrieves DNS records and resolves domain names into IP addresses.

---

# 📡 Step 5 — Trace Network Route

```bash
traceroute google.com
```

### Purpose

Shows the path packets travel across the network to reach a destination.

---

# 🌍 Step 6 — Fetch Remote Content

```bash
curl https://example.com
```

or

```bash
wget https://example.com
```

### Purpose

Downloads or retrieves data from web servers.

---

# 🔎 Step 7 — Check Listening Ports

```bash
ss -lnt
```

### Purpose

Displays listening TCP ports that may expose services to the network.

---

# 📊 Observations

During the investigation, we observed:

* The system’s assigned IP address
* Active network interfaces
* Open and listening ports
* External connectivity status
* DNS resolution results
* Remote server communication

---

# 🚨 Security Relevance

Network investigation is critical in cybersecurity because analysts often need to:

* Detect suspicious outbound connections
* Identify unauthorized services
* Investigate malware communication
* Monitor active remote sessions
* Analyze lateral movement inside networks

These skills are commonly used in:

* SOC operations
* Incident response
* Threat hunting
* System administration

---

# 🧠 Key Learnings

* Linux provides powerful built-in networking tools
* Active connections can reveal suspicious activity
* DNS investigation helps identify remote systems
* Open ports expose services to networks
* Network visibility is essential for incident detection

---

# ✅ Conclusion

This lab introduced foundational Linux network investigation techniques using common command-line utilities.

Understanding how systems communicate across networks is a core skill for SOC analysts and cybersecurity professionals, helping detect threats, troubleshoot connectivity issues, and investigate suspicious activity.
