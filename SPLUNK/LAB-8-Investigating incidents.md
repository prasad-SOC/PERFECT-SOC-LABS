# 🔎 Splunk Lab 8 — Investigating Incidents

## Objectives

By completing this lab, I learned how to:

✅ Identify suspicious events in large datasets  
✅ Pivot between related logs  
✅ Build an investigation timeline  
✅ Correlate users, hosts, IPs, and event IDs  
✅ Separate false positives from real incidents  
✅ Document findings like a SOC analyst  

---

## Lab Environment

### Data Source
- Windows security logs
- Authentication events
- System activity logs
- Network connection events

---

## Step 1 — Start With a Broad Search

Started by reviewing all available logs:

```spl
index=main
```

This gave a complete view of incoming events.

---

## Step 2 — Search for Suspicious Activity

Focused on authentication failures:

```spl
index=main EventCode=4625
```

Things investigated:

- Multiple failed logins
- Unusual usernames
- Repeated attempts from same source
- Logins outside normal hours

---

## Step 3 — Pivot Into Related Events

After finding suspicious events, pivoted using:

### Username

```spl
index=main username="<username>"
```

### Host

```spl
index=main host="<hostname>"
```

### Source IP

```spl
index=main src_ip="<ip>"
```

This helped connect related activity.

---

## Step 4 — Build Timeline

Used time-based analysis to understand:

- First event
- Last event
- Frequency
- Escalation pattern

Example query:

```spl
index=main EventCode=4625
| timechart count
```

---

## Step 5 — Correlate Successful Logins

Checked whether failed logins were followed by successful authentication:

```spl
index=main (EventCode=4625 OR EventCode=4624)
```

This helps detect possible brute-force success.

---

## Step 6 — Validate Context

Reviewed:

- Host behavior
- User behavior
- Historical activity
- Related system logs

Goal:

Determine whether activity is:

- Normal administrative behavior
- User mistake
- Potential attack

---

## Investigation Findings

### Observed

✅ Failed login attempts detected  
✅ Related user activity identified  
✅ Timeline reconstructed  
✅ Cross-event correlation performed  

### Analyst Conclusion

No confirmed malicious activity in this lab environment, but the investigation process mirrored real SOC triage workflows.

---

## Key Skills Practiced

- Log investigation
- Event correlation
- Timeline analysis
- IOC pivoting
- Incident triage
- Analytical documentation

---

## SOC Analyst Takeaway

A SOC analyst does not just search logs.

A SOC analyst asks:

> “What story are these logs telling?”

This lab strengthened my ability to investigate incidents systematically using :contentReference[oaicite:2]{index=2}.
