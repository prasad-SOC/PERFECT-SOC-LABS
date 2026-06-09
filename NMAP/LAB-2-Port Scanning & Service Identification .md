# Nmap Lab 2 — Port Scanning & Service Identification

## Objective

The objective of this lab is to learn how to identify open ports and discover services running on a target system using Nmap. Understanding open ports and exposed services is a fundamental skill for SOC analysts and security professionals because attackers often target vulnerable services to gain access to systems.

---

## Lab Environment

* Operating System: Kali Linux
* Tool Used: Nmap
* Target: Scanme.nmap.org (or a lab machine within a controlled environment)

---

## Skills Learned

* Understanding TCP ports
* Identifying open and closed ports
* Performing basic port scans
* Detecting running services
* Determining service versions
* Interpreting Nmap scan results

---

## Why This Lab Matters

Every network service listens on a specific port. By identifying open ports and the services behind them, security analysts can:

* Understand the attack surface of a system
* Detect unnecessary or risky services
* Verify system configurations
* Support vulnerability assessments
* Assist incident investigations

---

## Lab Tasks

### Task 1: Basic Port Scan

Scan a target host to discover open ports.

```bash
nmap scanme.nmap.org
```

#### Expected Outcome

* Identify open ports on the target.
* Observe Nmap's default scanning behavior.

---

### Task 2: Scan Specific Ports

Scan selected ports only.

```bash
nmap -p 22,80,443 scanme.nmap.org
```

#### Expected Outcome

* Determine whether the specified ports are open, closed, or filtered.

---

### Task 3: Scan All TCP Ports

Perform a full TCP port scan.

```bash
nmap -p- scanme.nmap.org
```

#### Expected Outcome

* Scan all 65,535 TCP ports.
* Identify additional services that may not appear in a default scan.

---

### Task 4: Service Detection

Identify services running on open ports.

```bash
nmap -sV scanme.nmap.org
```

#### Expected Outcome

* Discover service names.
* Gather service version information where available.

---

### Task 5: Combined Port Scan and Service Detection

Run a detailed scan.

```bash
nmap -p- -sV scanme.nmap.org
```

#### Expected Outcome

* Enumerate all TCP ports.
* Identify services and versions associated with open ports.

---

## Understanding Common Ports

| Port | Service |
| ---- | ------- |
| 21   | FTP     |
| 22   | SSH     |
| 23   | Telnet  |
| 25   | SMTP    |
| 53   | DNS     |
| 80   | HTTP    |
| 110  | POP3    |
| 143  | IMAP    |
| 443  | HTTPS   |
| 3389 | RDP     |

---

## Example Findings

Example output may reveal:

* Port 22 open → SSH service
* Port 80 open → HTTP service
* Port 443 open → HTTPS service

The exact results may vary depending on the target and network conditions.

---

## Key Takeaways

* Open ports indicate accessible network services.
* Service detection helps identify what is running behind a port.
* Version information can assist in vulnerability assessments.
* Nmap provides valuable visibility into a system's network exposure.

---

## Conclusion

In this lab, I practiced using Nmap to discover open ports and identify running services. I learned how to perform basic scans, full port scans, and service detection scans. These skills are essential for understanding network visibility, identifying potential security risks, and supporting security investigations.

---

## Commands Used

```bash
nmap scanme.nmap.org

nmap -p 22,80,443 scanme.nmap.org

nmap -p- scanme.nmap.org

nmap -sV scanme.nmap.org

nmap -p- -sV scanme.nmap.org
```
