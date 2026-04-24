# Wireshark Lab: File Download Detection

## Objective
Learn how to detect file downloads in network traffic using Wireshark by analyzing HTTP traffic, requests, responses, and transferred files.

## Tools Used
- Wireshark
- Sample PCAP file or live capture
- Windows/Linux system

## Lab Steps

### Step 1: Open Wireshark
Launch Wireshark and open the provided capture file or start a live packet capture.

### Step 2: Apply HTTP Filter
Use the following display filter:

http

This helps show only HTTP traffic.

### Step 3: Search for File Requests
Look for GET requests that may contain downloadable files such as:

.exe  
.zip  
.pdf  
.docx  
.txt

### Step 4: Inspect HTTP Conversations
Select suspicious packets and review:
- Requested file name
- Source IP
- Destination IP
- Host name
- URI path

### Step 5: Follow HTTP Stream
Right-click the packet and choose:

Follow → HTTP Stream

This helps rebuild the full file transfer conversation.

### Step 6: Check Server Response
Review the HTTP response for:
- Status code (200 OK)
- Content-Type
- Content-Length
- File data

### Step 7: Export Downloaded Objects
Go to:

File → Export Objects → HTTP

Check if downloadable files are available.

### Step 8: Document Findings
Record:
- File name
- Download source
- Protocol used
- File type
- Any suspicious indicators

## Key Learning Outcomes
- Detect file downloads in packet captures
- Analyze HTTP GET requests
- Reconstruct download sessions
- Export transferred files
- Identify suspicious downloads

## Conclusion
This lab improves practical skills in detecting downloaded files from network traffic, which is useful for SOC analysts during malware investigations and incident response.
