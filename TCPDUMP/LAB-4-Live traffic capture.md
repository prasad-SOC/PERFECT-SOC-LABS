
# Tcpdump Lab 4: Live Traffic Capture

## Objective
Learn how to capture live network traffic in real time using tcpdump and observe packets while browsing or generating traffic.

---

## Lab Setup
- Tool: tcpdump
- Environment: Linux Terminal / Kali Linux / Ubuntu
- Requirement: Root or sudo privileges

---

## Steps

### 1. Identify Available Network Interfaces
Use the following command:

```bash
tcpdump -D
````

This will list all available interfaces such as:

* eth0
* wlan0
* lo

Choose the active interface.

---

### 2. Start Live Packet Capture

```bash
sudo tcpdump -i eth0
```

Replace `eth0` with your active interface.

This starts capturing packets live.

---

### 3. Generate Traffic

While tcpdump is running:

* Open a website
* Ping a domain
* Use curl command
* Refresh browser pages

Example:

```bash
ping google.com
```

---

### 4. Observe Live Packets

You may see:

* Source IP
* Destination IP
* Protocol
* Port Numbers
* Packet Length

---

### 5. Stop Capture

Press:

```bash
Ctrl + C
```

This stops the capture and shows packet statistics.

---

## Useful Commands

### Capture limited packets

```bash
sudo tcpdump -i eth0 -c 20
```

### Show packet details

```bash
sudo tcpdump -i eth0 -v
```

### Save capture

```bash
sudo tcpdump -i eth0 -w livecapture.pcap
```

---

## Skills Learned

* Live packet sniffing
* Real-time traffic monitoring
* Identifying protocols
* Basic network troubleshooting
* Using tcpdump efficiently

---

## Conclusion

This lab helped understand how tcpdump captures traffic in real time. It is a powerful tool for monitoring, troubleshooting, and security investigations.

```
```
