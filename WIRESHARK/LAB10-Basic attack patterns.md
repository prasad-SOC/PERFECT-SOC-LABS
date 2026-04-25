# Wireshark Lab: Basic Attack Patterns

## Overview

In this lab, we used Wireshark to explore how common attack patterns can appear in network traffic. By analyzing packets, we can detect suspicious behavior and understand how attackers interact with systems.

## Objective

Learn to identify basic attack patterns through packet captures using Wireshark.

## Tools Used

* Wireshark
* Test network traffic / packet capture file

## Attack Patterns Covered

* Port Scanning
* Brute Force Login Attempts
* Suspicious DNS Requests
* Unusual HTTP Traffic
* Repeated Connection Attempts
* Unknown External Connections

## Steps Performed

### 1. Open Capture File

* Loaded the packet capture into Wireshark.
* Observed total traffic and active hosts.

### 2. Detect Port Scanning

* Checked for one source contacting many destination ports.
* Reviewed rapid SYN packet behavior.

### 3. Detect Brute Force Attempts

* Looked for repeated login requests or failed authentication traffic.
* Observed multiple connection retries in short time.

### 4. Analyze Suspicious DNS Activity

* Filtered DNS traffic.
* Checked for random or unusual domain requests.

### 5. Review HTTP Traffic

* Inspected HTTP requests and responses.
* Looked for strange URLs, downloads, or repeated requests.

### 6. Check Repeated Connections

* Observed continuous connection attempts from same source.
* Reviewed possible automated behavior.

### 7. Identify Unknown External IPs

* Checked outbound traffic to unfamiliar destinations.
* Reviewed communication patterns.

## Useful Wireshark Filters

```text
tcp
dns
http
tcp.flags.syn == 1 and tcp.flags.ack == 0
ip.addr == x.x.x.x
```

## Key Learnings

* Attack behavior often creates visible network patterns.
* Repetition and unusual traffic are important indicators.
* Wireshark helps detect scanning, brute force, and suspicious communication.
* Packet analysis improves investigation skills.

## Conclusion

This lab helped build practical skills in detecting basic attack patterns using Wireshark. Recognizing these behaviors is an important foundation for SOC analysts and defenders.
