---

# 🧪 LAB 5 — Process Tracking (Windows)

## 🎯 Objective

Monitor and analyze process activity on a Windows system using available tools and logs.

---

## 🖥️ Environment

* OS: Windows (Home Edition)
* Tools Used:

  * Event Viewer
  * Task Manager
  * Command Prompt

---

## ⚙️ Setup (Windows Home Compatible)

### 1. Enable Process Creation Auditing

Open **Command Prompt as Administrator** and run:

```
auditpol /set /subcategory:"Process Creation" /success:enable /failure:enable
```

---

### 2. Verify Auditing Status

```
auditpol /get /subcategory:"Process Creation"
```

---

### 3. Access Event Viewer

```
eventvwr.msc
```

Navigate to:

* Windows Logs → Security

---

## 🔍 Lab Tasks

### Step 1 — Generate Process Activity

* Open multiple applications (e.g., text editor, terminal, browser)
* Execute basic commands in terminal
* Open multiple browser tabs
* Close and reopen applications

---

### Step 2 — Observe Running Processes

* Open Task Manager
* Review:

  * Process Names
  * Process IDs (PID)
  * Resource usage

---

### Step 3 — Understand Process Relationships

* Identify how applications spawn additional processes
* Observe behavior differences between simple apps and complex applications

---

### Step 4 — Analyze Security Logs

* Open Event Viewer
* Navigate to:

  * Windows Logs → Security
* Locate process-related events

Focus on:

* Process creation events
* Associated metadata (process name, user, etc.)

---

### Step 5 — Behavioral Analysis

Evaluate observed processes:

* Are they expected?
* Do they align with user activity?
* Are there repeated or unusual executions?

---

### Step 6 — Cross-Verification

* Compare:

  * Active processes (Task Manager)
  * Logged events (Event Viewer)
* Identify any mismatches or patterns

---

### Step 7 — Documentation

Record:

* Applications executed
* Observed process behavior
* Any unusual findings
* General observations about system activity

---

## 🧠 Key Concepts

* Process monitoring
* Event-based detection
* PID tracking
* Basic behavioral analysis

---

## ⚠️ Limitations

* Windows Home Edition has restricted audit configuration
* Some log details (e.g., command-line arguments) may not be available
* Process hierarchy visibility is limited

---
