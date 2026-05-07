# Splunk Lab 1 — Searching Logs

## Objective
The goal of this lab was to understand how to search and analyze logs using Splunk.  
This is the first step in learning how SOC analysts investigate events, detect suspicious activity, and filter useful information from large datasets.

---

# Lab Setup

## Tool Used
- Splunk Enterprise

## Skills Practiced
- Basic log searching
- Understanding Splunk Search Processing Language (SPL)
- Filtering events
- Viewing timestamps and log sources
- Exploring indexed data

---

# Step 1 — Open Splunk Search & Reporting

After logging into Splunk, I opened the **Search & Reporting** app.

This section is used by analysts to:
- Search logs
- Investigate alerts
- Filter suspicious events
- Analyze system activity

---

# Step 2 — View All Logs

I started with a basic search:

```spl
index=*
````

This command displays all available indexed logs.

### Observation

* Large amount of events appeared
* Different log sources were visible
* Events contained timestamps, hosts, source types, and raw logs

---

# Step 3 — Search Specific Logs

Next, I searched for specific log categories.

Example:

```spl
index=* error
```

This helped filter logs containing the word **error**.

### Observation

* Only relevant logs were displayed
* Easier to investigate specific events
* Search became more focused

---

# Step 4 — Filter by Host

I practiced narrowing logs using hosts.

Example:

```spl
index=* host=server1
```

### Observation

* Logs from a single host appeared
* Reduced unnecessary data
* Improved investigation accuracy

---

# Step 5 — Search by Sourcetype

I also explored filtering by sourcetype.

Example:

```spl
index=* sourcetype=syslog
```

### Observation

* Splunk grouped logs based on source type
* Easier to analyze similar events together

---

# Key Learnings

Through this lab, I learned:

* How Splunk searches logs
* Importance of filtering events
* Basics of SPL queries
* How SOC analysts investigate log data
* How to reduce noise during investigations

---

# Conclusion

This lab provided a strong introduction to Splunk log searching.
Understanding how to search logs efficiently is one of the most important skills for SOC analysts because every investigation starts with finding the right data.
