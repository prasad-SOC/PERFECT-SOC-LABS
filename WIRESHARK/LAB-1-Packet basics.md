# 🧪 Wireshark Lab — Packet Basics

## 📌 Objective
Understand the fundamentals of network packets using Wireshark, including packet structure, protocols, and key fields used in network communication.

---

## 🛠️ Tools Used
- Wireshark

---

## 📚 Lab Overview
In this lab, we captured live network traffic and analyzed individual packets to understand how data is transmitted across a network.

---

## 🚀 Steps Performed

### 1. Start Packet Capture
- Open Wireshark
- Select the active network interface (Wi-Fi or Ethernet)
- Click on **Start Capturing Packets**

---

### 2. Generate Network Traffic
- Open a browser and visit any website (e.g., google.com)
- Let the capture run for 30–60 seconds

---

### 3. Stop Capture
- Click the **Stop** button in Wireshark

---

### 4. Select a Packet
- Click on any packet from the packet list pane

---

### 5. Analyze Packet Structure
Observe the three main sections:

#### 🔹 Packet List Pane
- Shows all captured packets
- Key columns:
  - Time
  - Source
  - Destination
  - Protocol
  - Length

#### 🔹 Packet Details Pane
Expand the following layers:

- **Frame**
  - Packet number
  - Frame length

- **Ethernet II**
  - Source MAC address
  - Destination MAC address

- **Internet Protocol (IP)**
  - Source IP address
  - Destination IP address

- **Transport Layer (TCP/UDP)**
  - Source port
  - Destination port

#### 🔹 Packet Bytes Pane
- Displays raw packet data in hexadecimal and ASCII format

---

### 6. Identify Key Fields
From the selected packet, note:

- Source IP:
- Destination IP:
- Protocol (TCP/UDP/ICMP):
- Source Port:
- Destination Port:

---

## 🔍 Key Learnings

- A packet is a small unit of data transmitted over a network
- Each packet contains multiple layers (Frame → Ethernet → IP → Transport)
- Wireshark helps visualize and analyze these layers in detail
- Understanding packets is essential for network troubleshooting and security analysis

---

## 🛡️ SOC Analyst Perspective

- Packet analysis helps detect:
  - Suspicious connections
  - Unauthorized communication
  - Network scanning activity
- It forms the foundation for advanced threat detection and incident investigation

---

## ✅ Conclusion

This lab introduced the basic structure of network packets and how to analyze them using Wireshark. These fundamentals are critical for progressing into deeper network traffic analysis and security monitoring.

---
