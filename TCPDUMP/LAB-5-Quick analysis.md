##Tcpdump Lab 5: Quick Analysis

# Tcpdump Lab 5: Quick Analysis

## Objective
Learn how to quickly analyze captured traffic using tcpdump by reading packet summaries, identifying active hosts, protocols, and suspicious communication patterns.

## Lab Setup
- Tool: tcpdump
- Environment: Kali Linux / Linux terminal
- Interface: eth0 (or your active interface)
- Permission: sudo access

## Steps

### 1. Start Quick Packet Capture
```bash
sudo tcpdump -i eth0
````

This begins live traffic capture with packet summaries.

---

### 2. Limit Packet Count for Fast Review

```bash
sudo tcpdump -i eth0 -c 20
```

Captures only 20 packets and exits automatically.

---

### 3. Disable Name Resolution for Faster Output

```bash
sudo tcpdump -i eth0 -n
```

Shows raw IP addresses and port numbers.

---

### 4. Capture Only TCP Traffic

```bash
sudo tcpdump -i eth0 tcp
```

Quickly focuses on TCP communication.

---

### 5. Capture Only DNS Requests

```bash
sudo tcpdump -i eth0 port 53
```

Useful for quick DNS analysis.

---

### 6. Show Source and Destination Hosts

Observe output fields:

* Source IP
* Destination IP
* Protocol
* Port numbers
* Packet flags

---

### 7. Save Capture for Later Analysis

```bash
sudo tcpdump -i eth0 -w quickanalysis.pcap
```

---

### 8. Read Saved Capture

```bash
tcpdump -r quickanalysis.pcap
```

---

## Key Learnings

* Perform quick traffic reviews in terminal
* Detect active systems
* Identify common protocols
* Use filters for faster analysis
* Save evidence for deeper investigation

## Real SOC Use Case

Analysts use quick tcpdump checks during incidents to rapidly inspect suspicious traffic before full packet analysis.

## Result

Successfully performed quick traffic analysis using tcpdump.

```
```
