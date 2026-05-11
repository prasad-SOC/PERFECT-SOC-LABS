 # Splunk Lab 5 — Correlation Basics

## Lab Overview
In this lab, I explored one of the most important concepts in Security Operations: **Correlation**.

Correlation helps SOC analysts connect multiple events from different sources and identify patterns that may indicate suspicious activity. Instead of looking at a single event, correlation helps build the bigger picture.

This lab focused on understanding how related events can be connected using Splunk searches.

---

## Objective
By completing this lab, I learned how to:

- Understand event correlation in Splunk
- Connect related security events
- Search across multiple hosts and sources
- Identify suspicious patterns using combined conditions
- Build an investigation mindset instead of reviewing isolated logs

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Platform | Splunk Enterprise |
| Data Source | Sample logs / generated events |
| Focus Area | Event Correlation |
| Skill Level | Beginner to Intermediate |

---

## Why Correlation Matters in SOC

Attackers rarely generate just one event.

A failed login may be followed by:
- Another failed login
- A successful login
- Access from a different host
- Privilege escalation
- File access activity

If analysts only investigate one event at a time, important attack patterns may be missed.

Correlation solves this problem.

---

## Step 1 — Open Splunk Search & Reporting

1. Log in to Splunk.
2. Navigate to:

Apps → Search & Reporting

3. Select the desired time range.

---

## Step 2 — View All Authentication Events

Use:

```spl
index=* "login"
````

This displays login-related events.

### Observation

Multiple authentication events appeared from different hosts and users.

---

## Step 3 — Search Failed Logins

Use:

```spl
index=* ("failed" AND "login")
```

### Observation

Failed authentication attempts became easier to isolate.

---

## Step 4 — Correlate Failed + Successful Logins

Use:

```spl
index=* ("failed" OR "success") "login"
```

### Observation

Now both failed and successful login attempts appeared together.

This makes it easier to identify:

* Brute-force attempts
* Password spraying
* Successful compromise after failures

---

## Step 5 — Group Events by User

Use:

```spl
index=* "login"
| stats count by user status
```

### Observation

This helped identify users with unusual authentication behavior.

---

## Step 6 — Group Events by Host

Use:

```spl
index=* "login"
| stats count by host status
```

### Observation

Some systems generated more authentication events than others.

---

## Step 7 — Time-Based Correlation

Use:

```spl
index=* "login"
| timechart count by status
```

### Observation

This helped visualize when failed or successful logins occurred.

---

## Key Learning

In this lab, I learned that:

* Individual logs tell stories
* Correlated logs reveal attacks
* Context matters in security investigations
* Splunk makes pattern detection much faster

---

## Skills Gained

✅ Event Correlation
✅ Authentication Investigation
✅ SPL Searching
✅ Statistical Analysis
✅ SOC Investigation Thinking

---

## Real SOC Use Cases

Correlation is used for detecting:

* Brute-force attacks
* Account compromise
* Lateral movement
* Privilege escalation
* Insider threats

---

## Final Thoughts

This lab helped me shift from simply reading logs to connecting events and identifying patterns.

That mindset is what transforms log analysis into real security investigation.
