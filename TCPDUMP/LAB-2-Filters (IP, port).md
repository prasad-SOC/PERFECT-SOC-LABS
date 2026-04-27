# Tcpdump Lab 2: Filters (IP, Port)

## Objective
Learn how to use tcpdump filters to capture specific traffic based on IP addresses and port numbers.

## Lab Setup
- Tool Used: tcpdump
- Environment: Local machine / safe lab setup
- Network Interface: Active network adapter (example: eth0, wlan0)

## Step 1: Identify Network Interface
Check available interfaces:

sudo tcpdump -D

## Step 2: Capture Traffic from a Specific IP
Replace with target IP:

sudo tcpdump -i <interface> host <IP_Address>

Example:

sudo tcpdump -i eth0 host 8.8.8.8

## Step 3: Capture Traffic from Source IP Only

sudo tcpdump -i <interface> src host <IP_Address>

## Step 4: Capture Traffic to Destination IP Only

sudo tcpdump -i <interface> dst host <IP_Address>

## Step 5: Capture Traffic on a Specific Port
Example HTTP traffic:

sudo tcpdump -i <interface> port 80

## Step 6: Capture Source Port Only

sudo tcpdump -i <interface> src port 53

## Step 7: Capture Destination Port Only

sudo tcpdump -i <interface> dst port 443

## Step 8: Combine IP and Port Filters

sudo tcpdump -i <interface> host <IP_Address> and port 443

## Step 9: Save Output to File

sudo tcpdump -i <interface> port 80 -w capture.pcap

## Key Learning
- Use IP filters to isolate traffic from devices.
- Use port filters to inspect service-based traffic.
- Combine filters for precise packet capture.
- Helps reduce noise during investigations.

## Conclusion
This lab improved understanding of tcpdump filtering techniques using IP addresses and ports for focused traffic analysis.
