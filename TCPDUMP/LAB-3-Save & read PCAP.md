# Tcpdump Lab 3: Save & Read PCAP

## Objective
Learn how to capture live network traffic into a `.pcap` file and read the saved capture later using tcpdump.

## Requirements
- Linux system / VM
- tcpdump installed
- Sudo privileges
- Active network connection

## Steps

### 1. List Available Interfaces
```bash
tcpdump -D
```

Identify the active network interface.

### 2. Start Capture and Save to PCAP

```bash
sudo tcpdump -i <interface> -w capture.pcap
```

Example:

```bash
sudo tcpdump -i eth0 -w capture.pcap
```

### 3. Generate Traffic

While capture is running:

* Open websites
* Ping any host
* Browse the internet

### 4. Stop Capture

Press:

```bash
Ctrl + C
```

### 5. Read Saved PCAP File

```bash
tcpdump -r capture.pcap
```

### 6. Read Without Name Resolution

```bash
tcpdump -nn -r capture.pcap
```

### 7. Apply Filters While Reading

Only TCP traffic:

```bash
tcpdump -r capture.pcap tcp
```

Only Port 80 traffic:

```bash
tcpdump -r capture.pcap port 80
```

## Skills Learned

* Save packet captures into PCAP files
* Read offline captures
* Use filters on saved traffic
* Perform basic traffic review with tcpdump

## Result

Successfully captured live packets and reviewed them later from a saved PCAP file.

```
```
