# Wireshark Lab 4 — HTTP Traffic Analysis

## Objective

Capture and analyze HTTP traffic in Wireshark to understand how web communication works between a client and a server.

---

## Tools Used

* Wireshark
* Linux Virtual Machine
* Internet Connection
* Web Browser

---

## Lab Scenario

Used Wireshark to capture live network traffic and filtered HTTP packets for protocol analysis.

---

## Steps Performed

### Step 1: Open Wireshark

Launch Wireshark inside the virtual machine.

### Step 2: Select Interface

Choose the active network interface.

### Step 3: Start Packet Capture

Begin live packet capture.

### Step 4: Apply HTTP Filter

Use the display filter:

`http`

### Step 5: Observe HTTP Traffic

Multiple HTTP packets were captured during browsing activity.

### Step 6: Inspect Packet Details

Reviewed packet information such as request and response communication, protocol layers, and session behavior.

### Step 7: Analyze Communication Flow

Observed how the client sends requests and how the server returns responses.

---

## Key Findings

* HTTP traffic can be filtered easily in Wireshark.
* Requests and responses help understand web communication.
* Packet details reveal useful protocol information.
* Traffic analysis improves visibility into network activity.

---

## SOC Analyst Relevance

Useful for detecting:

* Suspicious web traffic
* Unusual outbound connections
* Malicious web requests
* Data transfer activity
* Network anomalies
