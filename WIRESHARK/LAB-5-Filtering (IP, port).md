# Wireshark Lab: Filtering (IP, Port)

## Objective

Learn how to use Wireshark display filters to isolate packets using IP addresses and port numbers. This is an essential skill for network troubleshooting and SOC investigations.

---

## Lab Setup

* Install Wireshark
* Connect to a network
* Select active network adapter
* Start packet capture

---

## Step-by-Step Lab

### 1. Open Wireshark

Launch Wireshark and select the active interface.

### 2. Start Packet Capture

Click the shark fin icon.

### 3. Generate Network Traffic

Create traffic by:

* Browsing websites
* Running ping commands
* Opening applications

---

## IP Filters

### Source IP

```wireshark
ip.src == X.X.X.X
```

### Destination IP

```wireshark
ip.dst == X.X.X.X
```

### Any IP

```wireshark
ip.addr == X.X.X.X
```

---

## Port Filters

### HTTP Traffic

```wireshark
tcp.port == 80
```

### HTTPS Traffic

```wireshark
tcp.port == 443
```

### DNS Traffic

```wireshark
udp.port == 53
```

### Specific Source Port

```wireshark
tcp.srcport == XXXX
```

### Specific Destination Port

```wireshark
tcp.dstport == XXXX
```

---

## Combined Filters

### IP + Port

```wireshark
ip.addr == X.X.X.X && tcp.port == 443
```

### Multiple Ports

```wireshark
tcp.port == 80 || tcp.port == 443
```

---

## What to Observe

* Source IP
* Destination IP
* Port Numbers
* Protocol Type
* Packet Count
* Communication Pattern

---

## Key Learning

* Filters reduce noise
* IP filters identify hosts
* Port filters identify services
* Combined filters improve investigations

---

## SOC Use Cases

* Investigate suspicious IP communication
* Detect malware beaconing
* Review web traffic
* Analyze DNS requests
* Find unusual ports
