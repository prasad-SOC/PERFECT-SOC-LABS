# Splunk Lab 10 – Log Patterns

## Overview
The objective was to move beyond individual events and start recognizing repeated behaviors, anomalies, and recurring activity that may indicate operational issues or security threats.

Pattern recognition is a core SOC analyst skill because attackers often leave behind repeated traces in logs.

---

## Objectives
By completing this lab, I learned how to:

- Search and analyze large log datasets
- Identify repeated log events
- Detect frequency-based patterns
- Group similar events together
- Spot abnormal behavior inside normal traffic
- Use Splunk statistical commands for pattern analysis

---

## Lab Environment

### Platform
- Splunk Enterprise

### Data Source
- Sample security and system logs

### Skills Practiced
- Log analysis
- Event correlation
- Pattern detection
- Statistical analysis

---

## Step 1 – Open Splunk Search & Reporting

Navigate to:

Apps → Search & Reporting

Load the dataset for analysis.

---

## Step 2 – View Raw Events

Start with a broad search:

```spl
index=main
```

This displays all available events.

---

## Step 3 – Identify Event Frequency

Count repeated events:

```spl
index=main
| stats count by sourcetype
```

### Purpose
This helps identify which log sources generate the most events.

---

## Step 4 – Detect Repeated Actions

Group similar actions:

```spl
index=main
| stats count by action
```

### Purpose
Useful for identifying repetitive behaviors such as:

- login
- logout
- failed authentication
- file access

---

## Step 5 – Find User Activity Patterns

Analyze user behavior:

```spl
index=main
| stats count by user
```

### Purpose
Helps identify:

- Highly active users
- Unusual user behavior
- Potential compromised accounts

---

## Step 6 – Detect Failed Login Patterns

Search for authentication failures:

```spl
index=main "failed"
| stats count by src_ip
```

### Purpose
Useful for spotting:

- Brute force attempts
- Password spraying
- Misconfigured services

---

## Step 7 – Analyze Time-Based Patterns

View activity over time:

```spl
index=main
| timechart count
```

### Purpose
Helps detect:

- Activity spikes
- Quiet periods
- Scheduled tasks
- Suspicious bursts

---

## Key Learnings

✅ Logs tell stories through repetition  
✅ Patterns often reveal hidden threats  
✅ Statistical analysis simplifies investigation  
✅ Frequency analysis helps prioritize alerts  
✅ Time-based analysis exposes anomalies  

---

## SOC Analyst Takeaway

A SOC analyst does not only investigate single alerts.

A SOC analyst looks for patterns:

- Who is repeating actions?
- What events occur most frequently?
- When does unusual activity happen?
- Which systems generate abnormal logs?

Pattern recognition turns raw logs into actionable intelligence.

---

## Tools Used

- Splunk Enterprise
- Search Processing Language (SPL)
