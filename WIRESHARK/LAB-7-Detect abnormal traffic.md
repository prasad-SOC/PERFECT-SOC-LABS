# Wireshark Lab: Detect Abnormal Traffic

## Objective

Learn how to detect unusual or suspicious traffic patterns using Wireshark.

## Lab Setup

* Tool Used: Wireshark
* Capture Type: Live traffic or PCAP file
* Goal: Identify abnormal network behavior

## Steps Performed

### 1. Open Wireshark

Launch Wireshark and select the active network interface.

### 2. Start Capture

Begin live packet capture or open the provided capture file.

### 3. Observe Traffic

Monitor common protocols:

* TCP
* UDP
* DNS
* HTTP
* ICMP

### 4. Detect Suspicious Indicators

Look for:

* High packet volume
* Repeated requests
* Failed connections
* Unusual ports
* Excessive DNS queries
* ICMP floods
* Retransmissions
* Reset packets

### 5. Apply Filters

```wireshark
dns
icmp
tcp.flags.syn == 1 && tcp.flags.ack == 0
tcp.analysis.retransmission
ip.addr == x.x.x.x
```

### 6. Use Statistics

* Protocol Hierarchy
* Conversations
* Endpoints
* IO Graphs

### 7. Follow Streams

Right-click suspicious packets:

* Follow TCP Stream
* Follow UDP Stream

## Learning Outcomes

* Identify abnormal traffic
* Use filters for detection
* Analyze suspicious behavior
* Improve investigation skills

## SOC Relevance

Useful for:

* Threat hunting
* Malware traffic detection
* Scan detection
* Network troubleshooting

## Conclusion

This lab improved practical skills in detecting suspicious network traffic using Wireshark.
