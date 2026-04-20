# Wireshark Lab: Follow Streams

## Objective
Learn how to use the **Follow Streams** feature in Wireshark to reconstruct and analyze complete conversations between two devices. This helps in understanding what data was exchanged during a network session.

## Tools Required
- Wireshark
- Sample packet capture file (.pcap) or live network traffic

## Lab Setup
1. Open Wireshark.
2. Start capturing traffic or open an existing `.pcap` file.
3. Generate some network traffic such as:
   - Browsing a website
   - Using HTTP service
   - Sending a request to a server

## Steps to Perform

### Step 1: Open the Capture File
- Launch Wireshark.
- Open the packet capture file or use live traffic.

### Step 2: Identify a Conversation
- Look through the packet list.
- Find packets related to protocols such as:
  - TCP
  - HTTP
  - Telnet
  - FTP

### Step 3: Select a Packet
- Click on any packet that belongs to the conversation you want to inspect.

### Step 4: Use Follow Streams
- Right-click the selected packet.
- Choose one of the following:
  - **Follow TCP Stream**
  - **Follow UDP Stream**
  - **Follow HTTP Stream** (if available)

### Step 5: Analyze the Conversation
- A new window will open showing the complete communication between client and server.
- Observe:
  - Requests
  - Responses
  - Commands
  - Plain text data (if unencrypted)

### Step 6: Apply Auto Filter
- Wireshark may automatically filter only packets from that stream.
- Review the packet list to see only related packets.

### Step 7: Return to Full Capture
- Clear the filter bar to view all packets again.

## Key Learning Points
- Follow Streams reconstructs full conversations from packets.
- Helps identify requests and responses quickly.
- Useful for investigating suspicious traffic.
- Useful for checking if sensitive data is sent in plain text.
- Saves time compared to reading packets one by one.

## Real-World Use Cases
- Investigating malware communication
- Reviewing HTTP login requests
- Checking suspicious outbound traffic
- Troubleshooting application issues
- Understanding attacker command sessions

## Conclusion
The Follow Streams feature is one of the most powerful tools in Wireshark. It allows analysts to rebuild conversations and quickly understand what happened during a network session.
