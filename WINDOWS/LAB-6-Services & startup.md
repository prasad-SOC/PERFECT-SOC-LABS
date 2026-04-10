# 🧪 Lab: Windows Services & Startup Analysis

## 🎯 Objective
The goal of this lab is to understand how Windows services and startup programs operate, and how they can be analyzed to identify suspicious or persistence-related activity from a SOC analyst perspective.

---

## 🖥️ Lab Environment
- Operating System: Windows 10 / Windows 11 / Windows Server
- Tools Used:
  - Task Manager
  - Services Manager (`services.msc`)
  - System Configuration (`msconfig`)
  - Registry Editor (`regedit`)

---

## 📌 Lab Tasks

### 1. Explore Windows Services
- Open **Services Manager**
- Identify:
  - Running services
  - Stopped services
  - Startup types (Automatic / Manual / Disabled)

---

### 2. Analyze Service Properties
- Select multiple services and review:
  - Service Name vs Display Name
  - Executable Path
  - Startup Type
- Observe any unusual naming conventions or file paths

---

### 3. Identify Critical System Services
- Locate services related to:
  - Security
  - Networking
  - Authentication
- Understand their default behavior and importance

---

### 4. Investigate Startup Programs (Task Manager)
- Open **Task Manager → Startup Tab**
- Review:
  - Enabled vs Disabled programs
  - Publisher details
  - Startup impact

---

### 5. Cross-Check with System Configuration
- Open **msconfig**
- Compare startup entries with Task Manager
- Identify any inconsistencies

---

### 6. Analyze Registry Startup Locations
- Navigate to the following registry paths:
  - `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run`
  - `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`
- List all startup entries

---

### 7. Identify Suspicious Entries
- Look for:
  - Unknown or unsigned executables
  - Missing publisher information
  - Unusual file locations (e.g., Temp, AppData)
  - Random or obfuscated names

---

### 8. Apply SOC Thinking
- Evaluate:
  - Is the service or program expected on this system?
  - Does it relate to a known application?
  - Could it indicate persistence?

---

## 🧠 Key Concepts
- Windows Services Management
- Startup Program Analysis
- Persistence Mechanisms
- Behavioral Analysis in SOC Operations

---

## 📍 Expected Outcome
By completing this lab, you should be able to:
- Analyze Windows services effectively
- Investigate startup programs across multiple system locations
- Recognize potential persistence techniques
- Differentiate between normal and suspicious behavior

---

## ⚠️ Notes
- This lab focuses on analysis, not removal or remediation
- Avoid modifying or disabling critical system services
- Observations may vary depending on the system environment

---

## 🔍 SOC Insight
Startup locations and services are commonly used by attackers to maintain persistence. Understanding normal system behavior is essential before identifying anomalies.

---
