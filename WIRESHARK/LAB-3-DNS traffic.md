# Wireshark Lab 3: DNS Traffic Analysis

## Objective

Capture and analyze DNS traffic using Wireshark to understand how domain names are translated into IP addresses.

---

## Tools Required

* Wireshark
* Internet connection
* Browser or Command Prompt

---

## Step 1: Open Wireshark

1. Launch Wireshark.
2. Select your active network adapter.
3. Start packet capture.

---

## Step 2: Generate DNS Traffic

### Browser Method

Visit websites such as:

* google.com
* openai.com
* wikipedia.org

### Command Prompt Method

```cmd
nslookup google.com
nslookup openai.com
nslookup wikipedia.org
```

---

## Step 3: Stop Capture

1. Return to Wireshark.
2. Click the Stop button.

---

## Step 4: Apply DNS Filter

```wireshark
dns
```

This displays only DNS packets.

---

## Step 5: Analyze DNS Queries

Look for packets like:

* Standard query A google.com
* Standard query A openai.com

Observe:

* Source IP
* Destination IP
* Query Name
* Query Type (A / AAAA)

---

## Step 6: Analyze DNS Responses

Look for:

* Standard query response

Observe:

* Returned IP addresses
* Response time
* Multiple answers
* CNAME records

---

## Step 7: Match Query and Response

Compare:

* Transaction ID
* Domain name
* Returned answer

---

## Step 8: Useful Filters

### Only Queries

```wireshark
dns.flags.response == 0
```

### Only Responses

```wireshark
dns.flags.response == 1
```

### Search Specific Domain

```wireshark
dns.qry.name contains google
```

---

## Key Learnings

* DNS translates names to IP addresses.
* Website access usually starts with DNS.
* DNS traffic helps analysts investigate threats.

---

## SOC Use Cases

* Detect malicious domains
* Investigate phishing activity
* Identify DNS tunneling
* Monitor suspicious outbound traffic
