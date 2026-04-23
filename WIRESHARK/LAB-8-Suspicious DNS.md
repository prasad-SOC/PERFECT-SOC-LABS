# Wireshark Lab: Suspicious DNS Traffic Analysis

## Objective
Learn how to identify suspicious DNS activity using Wireshark by analyzing DNS queries, responses, unusual domains, and traffic patterns that may indicate malware communication or data exfiltration.

## Tools Used
- Wireshark
- Sample PCAP file or live network capture
- Windows / Linux system

## Lab Steps

### Step 1: Open Wireshark
Launch Wireshark and open the provided capture file or start a live capture.

### Step 2: Apply DNS Filter
Use the display filter:

dns

This will show only DNS-related packets.

### Step 3: Review DNS Queries
Check:
- Requested domain names
- Query types (A, AAAA, TXT, MX, etc.)
- Repeated requests
- Failed lookups

### Step 4: Identify Suspicious Indicators
Look for:
- Random or strange domain names
- Very long subdomains
- Large number of DNS requests
- Repeated NXDOMAIN responses
- TXT record lookups
- Traffic to unknown external DNS servers

### Step 5: Inspect Source Systems
Find which internal IP address generated the suspicious DNS traffic.

### Step 6: Analyze Timing Patterns
Check if DNS requests happen in fixed intervals, which may indicate beaconing activity.

### Step 7: Use Statistics
Go to:
Statistics > Endpoints  
Statistics > Conversations

Review top talkers and DNS-heavy hosts.

### Step 8: Document Findings
Record:
- Source IP
- Queried domains
- Frequency
- Response types
- Any suspicious behavior observed

## Key Learning Outcomes
- Understand normal vs suspicious DNS behavior
- Detect possible malware C2 traffic
- Identify DNS tunneling signs
- Use Wireshark filters for DNS analysis
- Improve threat hunting skills

## Common Wireshark Filters
dns  
dns.qry.name  
dns.flags.rcode != 0  
ip.addr == x.x.x.x

## Conclusion
DNS traffic can reveal hidden malicious activity. By reviewing unusual requests, failed lookups, and repetitive patterns, analysts can detect threats early.
