# Nmap Lab 3 — Operating System Detection

## Objective

The objective of this lab is to learn how Nmap identifies the operating system running on a target host. Operating System (OS) detection helps security analysts gather information about devices on a network and understand the environment before conducting further investigations.

---

## Lab Setup

### Attacker Machine

* Kali Linux
* Nmap installed

### Target Machine

* Metasploitable 2
* Ubuntu/Linux host (optional)
* Windows host (optional)

### Network

* Local Virtual Lab Environment

---

## Skills Learned

* Understanding OS fingerprinting
* Using Nmap OS detection features
* Identifying Linux and Windows systems
* Interpreting Nmap scan results
* Understanding limitations of OS detection

---

## Commands Used

### Basic OS Detection

```bash
sudo nmap -O <target-ip>
```

### Aggressive Scan (Includes OS Detection)

```bash
sudo nmap -A <target-ip>
```

### Verbose OS Detection

```bash
sudo nmap -O -v <target-ip>
```

### OS Detection with Version Detection

```bash
sudo nmap -O -sV <target-ip>
```

---

## Lab Steps

### Step 1: Verify Target Connectivity

Ping the target host to ensure it is reachable.

```bash
ping <target-ip>
```

---

### Step 2: Run Basic OS Detection

Use the OS detection flag.

```bash
sudo nmap -O <target-ip>
```

Nmap analyzes responses from the target and compares them against its OS fingerprint database.

---

### Step 3: Review OS Information

Look for output similar to:

```text
OS details: Linux 2.6.X
Network Distance: 1 hop
```

Review the detected operating system and confidence level.

---

### Step 4: Perform Aggressive Scan

Run an aggressive scan to gather additional information.

```bash
sudo nmap -A <target-ip>
```

This provides:

* OS detection
* Service detection
* Version detection
* Script scanning
* Traceroute information

---

### Step 5: Analyze Results

Review:

* Operating system detected
* Device type
* Open services
* Network distance
* Accuracy of the fingerprint

---

## Sample Output

```text
OS details: Linux 2.6.9 - 2.6.33
Device type: general purpose
Running: Linux
Network Distance: 1 hop
```

---

## Why OS Detection Matters

Security analysts use OS detection to:

* Identify devices on a network
* Understand attack surfaces
* Prioritize vulnerabilities
* Assist incident investigations
* Support asset inventory efforts

---

## Key Takeaways

* Nmap can estimate the operating system of a target host.
* OS detection relies on TCP/IP fingerprinting techniques.
* Root privileges are usually required for accurate detection.
* Results may vary depending on firewall rules and network configurations.
* OS detection is valuable during reconnaissance and security assessments.

---

## Conclusion

In this lab, I learned how to perform Operating System Detection using Nmap. By analyzing network responses, Nmap was able to estimate the operating system running on the target machine. This skill is useful for network reconnaissance, asset identification, and security investigations performed by SOC analysts and security professionals.
