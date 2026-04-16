# 📘 Wireshark Lab 2 — TCP 3-Way Handshake Analysis

## 🎯 Objective

To capture and analyze the TCP 3-way handshake using Wireshark and understand how connections are established.

---

## 🧠 Concept Overview

TCP uses a **3-step handshake** to establish a connection:

1. **SYN** → Client initiates connection
2. **SYN-ACK** → Server responds and acknowledges
3. **ACK** → Client confirms

👉 After this, communication begins.

---

## 🛠️ Lab Setup

* Tool: Wireshark
* Active internet connection
* Web browser (to generate traffic)

---

## 🔍 Step-by-Step Procedure

### Step 1: Start Packet Capture

* Open Wireshark
* Select your active network interface (Wi-Fi/Ethernet)
* Click **Start Capture**

---

### Step 2: Generate Network Traffic

* Open your browser
* Visit any website (e.g., google.com)

👉 This generates TCP connections

---

### Step 3: Apply Filter

Use the following filter:

```
tcp.flags.syn == 1
```

👉 Displays packets involved in connection initiation

---

### Step 4: Identify the TCP Handshake

Look for a sequence of 3 packets:

1. **SYN**

   * SYN = 1, ACK = 0

2. **SYN, ACK**

   * SYN = 1, ACK = 1

3. **ACK**

   * SYN = 0, ACK = 1

👉 These three packets form one complete TCP handshake

---

### Step 5: Analyze Packet Details

Click on each packet and observe:

* Source IP & Destination IP
* Source Port & Destination Port
* TCP Flags (SYN, ACK)
* Sequence Number
* Acknowledgment Number

---

## 🔑 Key Observations

* Every TCP connection starts with a handshake
* Multiple connections = multiple handshakes
* Port 443 indicates HTTPS traffic
* Client uses random (ephemeral) ports

---

## 🚨 SOC Use Case

* Detect connection attempts to external servers
* Identify abnormal patterns (e.g., repeated SYNs)
* Analyze potential scanning or DoS activity

---

## 📌 Conclusion

Understanding the TCP handshake helps in:

* Network troubleshooting
* Traffic analysis
* Detecting suspicious behavior

---
