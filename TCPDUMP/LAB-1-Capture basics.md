# tcpdump Lab 1: Capture Basics

## Overview

In this lab, we explored the basics of packet capturing using tcpdump. The objective was to understand how tcpdump captures live network traffic from a selected network interface and displays packets directly in the terminal.

## Objective

* Learn how to start tcpdump
* Identify available network interfaces
* Capture live packets
* Understand packet output format
* Stop packet capture safely

## Requirements

* Linux system / VM
* Terminal access
* tcpdump installed
* Sudo privileges

## Steps Performed

### 1. List Available Interfaces

```bash
tcpdump -D
```

### 2. Start Basic Packet Capture

```bash
sudo tcpdump -i <interface>
```

### 3. Generate Some Network Traffic

```bash
ping google.com
```

### 4. Observe Captured Packets

Review live packet output in the terminal. Typical fields include:

* Timestamp
* Source IP
* Destination IP
* Protocol
* Port numbers

### 5. Stop Capture

```bash
Ctrl + C
```

### 6. Review Capture Summary

After stopping, tcpdump displays:

* Packets captured
* Packets received by filter
* Packets dropped by kernel

## What I Learned

* How tcpdump captures traffic in real time
* How to choose the correct interface
* How packet data appears in terminal output
* Why tcpdump is useful for fast traffic inspection

## Conclusion

This lab gave a solid foundation in tcpdump basics and live packet capture, which is useful for network troubleshooting and SOC monitoring.
