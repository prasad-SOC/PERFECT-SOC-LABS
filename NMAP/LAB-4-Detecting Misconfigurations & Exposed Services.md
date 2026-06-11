# Nmap Lab 4 — Detecting Misconfigurations & Exposed Services

## Lab Overview

In this lab, I used Nmap to identify potentially exposed services and common security misconfigurations on a target system. The goal was to understand how attackers and security analysts can discover unnecessary open services, outdated configurations, and information disclosure risks during network reconnaissance.

---

## Objectives

* Identify open ports and running services
* Detect service versions
* Discover potentially exposed administrative services
* Analyze security risks associated with open services
* Understand the importance of reducing attack surface

---

## Lab Environment

| Component        | Details                                   |
| ---------------- | ----------------------------------------- |
| Tool Used        | Nmap                                      |
| Operating System | Kali Linux                                |
| Target           | Metasploitable2 / Vulnerable Test Machine |
| Network Type     | Local Lab Environment                     |

---

## Commands Used

### 1. Service Version Detection

```bash
nmap -sV <target-ip>
```

Purpose:

* Identify service versions running on open ports.

---

### 2. Aggressive Scan

```bash
nmap -A <target-ip>
```

Purpose:

* Detect operating system
* Discover service versions
* Run default NSE scripts
* Perform traceroute

---

### 3. Full TCP Port Scan

```bash
nmap -p- <target-ip>
```

Purpose:

* Scan all 65,535 TCP ports.
* Detect services that may be running on non-standard ports.

---

### 4. Service Enumeration

```bash
nmap -sV -sC <target-ip>
```

Purpose:

* Detect service versions.
* Execute default Nmap Scripting Engine (NSE) scripts.

---

## Findings

### Open Services Discovered

Example:

| Port | Service | State |
| ---- | ------- | ----- |
| 21   | FTP     | Open  |
| 22   | SSH     | Open  |
| 23   | Telnet  | Open  |
| 80   | HTTP    | Open  |
| 3306 | MySQL   | Open  |

---

### Potential Misconfigurations Identified

#### FTP Service Exposed

Risk:

* Anonymous login may be enabled.
* Files could be accessed without authentication.

#### Telnet Service Running

Risk:

* Credentials transmitted in plain text.
* Vulnerable to network sniffing attacks.

#### Database Port Exposed

Risk:

* MySQL service accessible from the network.
* May allow unauthorized access if weak credentials exist.

#### Excessive Open Ports

Risk:

* Increased attack surface.
* More opportunities for attackers to find vulnerabilities.

---

## Security Analysis

During the scan, multiple services were exposed to the network. Services such as Telnet and FTP are commonly considered high-risk if not properly secured. Open administrative or database services can provide valuable information to attackers during reconnaissance.

The results demonstrate how Nmap can quickly identify systems that may require further security review and hardening.

---

## Key Learning Outcomes

* Learned how to detect exposed network services.
* Understood the importance of service version detection.
* Identified common security misconfigurations.
* Practiced analyzing risks associated with open ports.
* Improved reconnaissance and enumeration skills using Nmap.

---

## Skills Practiced

* Network Reconnaissance
* Service Enumeration
* Vulnerability Discovery
* Security Assessment
* Attack Surface Analysis
* Nmap Scanning Techniques

---

## Conclusion

This lab demonstrated how Nmap can be used to detect exposed services and identify potential security misconfigurations. By analyzing open ports and service information, I gained practical experience in assessing attack surfaces and understanding how security weaknesses can be discovered during the reconnaissance phase of a security assessment.
