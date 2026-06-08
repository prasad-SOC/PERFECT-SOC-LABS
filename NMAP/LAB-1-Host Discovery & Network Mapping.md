# Nmap Lab 1 – Host Discovery & Network Mapping

## Overview

This lab focuses on discovering active hosts within a network using Nmap. Host discovery is one of the first steps in network enumeration and security assessments, helping analysts identify live systems before performing deeper investigations.

By completing this lab, I learned how to identify active devices, document discovered hosts, and create a basic network map.

---

## Objectives

* Discover active hosts on a network
* Understand Nmap host discovery techniques
* Identify IP addresses of live systems
* Collect MAC address information
* Create a basic network map
* Save and review scan results

---

## Tools Used

* Nmap
* Kali Linux
* Local Lab Network

---

## Lab Tasks

### 1. Verify Network Information

Identify the local IP address and network range.

```bash
ip a
```

or

```bash
ifconfig
```

---

### 2. Discover Live Hosts

Perform a ping scan to identify active devices.

```bash
nmap -sn 192.168.1.0/24
```

---

### 3. Save Scan Results

Store scan output for future analysis.

```bash
nmap -sn 192.168.1.0/24 -oN host_discovery.txt
```

---

### 4. Identify MAC Addresses

Run the scan with sufficient privileges to collect MAC address information.

```bash
sudo nmap -sn 192.168.1.0/24
```

---

### 5. Create a Network Map

Document discovered devices and their roles within the network.

Example:

```text
192.168.1.1   Router
192.168.1.5   Workstation
192.168.1.10  Kali Linux
192.168.1.20  Ubuntu VM
```

---

### 6. Scan Individual Hosts

Verify host availability.

```bash
nmap -sn 192.168.1.5
```

---

## Key Concepts Learned

* Host Discovery
* Network Enumeration
* Asset Identification
* Network Visibility
* Scan Result Documentation
* Basic Network Mapping

---

## Why This Matters for SOC Analysts

Host discovery helps security analysts:

* Identify active devices on a network
* Detect unauthorized systems
* Validate asset inventories
* Support incident investigations
* Establish network visibility before deeper analysis

---

## Skills Gained

* Nmap Fundamentals
* Host Discovery Techniques
* Network Mapping
* Documentation of Findings
* Basic Network Reconnaissance

---

## Outcome

Successfully discovered active hosts within a network, documented scan results, identified devices, and created a basic network map using Nmap.
