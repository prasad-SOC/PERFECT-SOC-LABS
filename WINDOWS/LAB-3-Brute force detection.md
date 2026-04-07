# 🔍 Lab 3: Brute Force Detection (Windows Event Logs)

## 🎯 Objective
Detect and analyze potential brute force login activity using Windows Security logs by identifying abnormal authentication patterns.

---

## 🧠 Background
Brute force attacks involve repeated login attempts to guess user credentials.  
Windows systems log authentication activity, which can be analyzed to detect such behavior.

---

## 🛠️ Requirements
- Windows system (VM or physical)
- Event Viewer access
- User account for testing

---

## 📁 Lab Setup
1. Ensure Security logging is enabled.
2. Generate authentication activity:
   - Perform multiple failed login attempts.
   - Optionally wait for lockout/reset conditions.
   - Perform a successful login after failed attempts.

---

## 🚀 Procedure

### Step 1: Access Logs
Open:
Event Viewer → Windows Logs → Security

---

### Step 2: Identify Authentication Events
Locate events related to:
- Failed login attempts
- Successful logins
- Account lockouts (if applicable)

---

### Step 3: Filter Relevant Logs
Apply filters based on:
- Authentication-related events
- Time range of generated activity

---

### Step 4: Analyze Failed Login Attempts
Examine:
- Frequency of failed attempts
- Targeted account(s)
- Time intervals between attempts
- Source system or IP

---

### Step 5: Correlate Events
Check for:
- Successful logins following failed attempts
- Matching usernames and sources
- Time proximity between events

---

### Step 6: Identify Suspicious Patterns
Evaluate for:
- High number of login failures
- Rapid succession of attempts
- Repeated targeting of specific account(s)
- Unusual login sources

---

### Step 7: Document Findings
Record:
- Account(s) involved
- Number of failed attempts
- Time window of activity
- Source (IP / system)
- Presence of successful login after failures

---

## 📊 Expected Outcome
- Ability to detect abnormal login behavior
- Understanding of authentication log patterns
- Identification of potential brute force indicators

---

## ⚠️ Notes
- A single failed login is normal behavior.
- Multiple failures may indicate user error or malicious intent.
- Brute force detection depends on pattern, volume, and context—not a fixed threshold.

---

## 🧭 Analyst Approach
- Distinguish normal vs abnormal behavior
- Correlate multiple events before concluding
- Avoid assumptions based on a single indicator

---

## ✅ Completion Criteria
- Relevant logs identified and filtered
- Authentication patterns analyzed
- Suspicious activity evaluated logically
- Findings documented clearly

---
