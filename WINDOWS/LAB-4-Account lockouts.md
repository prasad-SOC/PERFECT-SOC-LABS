# 🔐 SOC Lab 4 — Account Lockout Analysis (Windows Event Logs)

## 🎯 Objective

Analyze account lockout events using Windows Security logs and determine whether the activity represents normal behavior, misconfiguration, or potential security threats.

---

## 🧪 Lab Environment

* Windows Operating System
* Administrative access
* Event Viewer

---

## ⚙️ Setup

### Step 1 — Configure Account Lockout Policy

Open Command Prompt as Administrator and run:

```
net accounts /lockoutthreshold:3
net accounts /lockoutduration:5
net accounts /lockoutwindow:5
```

Verify configuration:

```
net accounts
```

---

### Step 2 — Prepare Test Account

Create a test user account:

```
net user testuser Password123 /add
```

---

### Step 3 — Generate Lockout Activity

Simulate login behavior:

* Lock the system (`Win + L`)
* Attempt login using the test account with incorrect password
* Repeat until the account is locked

---

## 🧭 Tasks

### Task 1 — Access Security Logs

* Open Event Viewer
* Navigate to:

  ```
  Windows Logs → Security
  ```

---

### Task 2 — Identify Lockout Events

Locate relevant events:

* Account lockout → Event ID 4740
* Failed login attempts → Event ID 4625

---

### Task 3 — Filter Relevant Logs

Apply filters based on:

* Event IDs (4740, 4625)
* Time range of generated activity

---

### Task 4 — Analyze Lockout Event Details

Examine:

* Target account name
* Caller computer name
* Time of lockout
* Event source

---

### Task 5 — Correlate Failed Login Attempts

Analyze:

* Number of failed attempts before lockout
* Username consistency
* Source system consistency
* Time proximity between events

---

### Task 6 — Pattern Identification

Evaluate for patterns such as:

* Repeated failed attempts leading to lockout
* Activity from a single or multiple sources
* Frequency and timing of attempts

---

### Task 7 — Activity Assessment

Determine whether the observed behavior is:

* Normal user behavior
* Misconfiguration
* Suspicious or malicious activity

---

## 📊 Expected Outcome

* Ability to identify account lockout events
* Ability to correlate authentication failures with lockouts
* Understanding of login behavior patterns
* Ability to classify activity based on evidence

---

## ⚠️ Notes

* A lockout event alone does not indicate malicious activity
* Multiple failed attempts may result from user error or system issues
* Accurate analysis depends on correlation and context

---

## 🧭 Analyst Approach

* Focus on patterns rather than isolated events
* Correlate multiple logs before drawing conclusions
* Validate source and context before classification

---

## ✅ Completion Criteria

* Lockout events identified and analyzed
* Related authentication events correlated
* Patterns evaluated logically
* Activity classification supported by evidence

---
