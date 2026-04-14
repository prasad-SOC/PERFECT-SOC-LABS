# 🛡️ SOC Lab — Admin Actions Analysis (Windows)

## 📌 Lab Overview

This lab focuses on monitoring and analyzing **administrative actions** in a Windows environment using Event Viewer. Administrative activities are high-impact events and play a critical role in detecting **privilege abuse, insider threats, and post-compromise behavior**.

---

## 🎯 Objective

* Identify and analyze administrative activities in Windows Security logs
* Understand how user and group changes are recorded
* Detect suspicious privilege-related actions
* Correlate admin actions with potential attack patterns

---

## 🧰 Tools Used

* Windows Event Viewer

---

## ⚙️ Lab Setup

* Windows system with administrative access
* Event logging enabled (default in most systems)

---

## 🔍 Steps Performed (Command Line + GUI)

### 🧑‍💻 Step 1: Open Event Viewer (Command Line)

```bash
eventvwr
```

---

### 📂 Step 2: Navigate to Security Logs

* Go to:
  `Windows Logs → Security`

---

### 🎯 Step 3: Filter Relevant Event IDs (Command Line Option)

```bash
EventID=4720 or EventID=4726 or EventID=4732 or EventID=4733 or EventID=4672 or EventID=4719
```

---

### 🔎 Step 4: Analyze Key Events

#### 👤 User Account Changes

* **4720** → User account created
* **4726** → User account deleted

#### 👥 Group Membership Changes

* **4732** → User added to a security group
* **4733** → User removed from a group

#### 🔐 Privilege & Policy Changes

* **4672** → Special privileges assigned (admin login)
* **4719** → Audit policy changed

---

### 🧠 Step 5: Investigate Event Details

For each event, analyze:

* Account performing the action
* Target account
* Time of activity
* Type of change

---

## 📊 Key Observations

* Administrative actions generate **high-value security logs**
* Privileged accounts leave clear traces when making changes
* Multiple admin events in a short time can indicate suspicious behavior

---

## 🚨 Detection Use Cases

### 1. Privilege Escalation

* Detect when a user is added to the **Administrators group**

### 2. Persistence Mechanism

* Creation of new user accounts for continued access

### 3. Policy Tampering

* Changes in audit policies to hide activity

---

## 🔗 Example Attack Flow

1. User login (Event ID 4624)
2. Admin privileges assigned (4672)
3. New account created (4720)
4. Added to admin group (4732)

---

## ✅ SOC Analyst Checklist

* Verify if the admin action is expected
* Check timing of activity
* Look for repeated or bulk changes
* Identify unknown or newly created accounts
* Correlate with login events

---

## 🧠 Key Takeaways

* Admin actions are **high-impact and high-risk events**
* Even a single suspicious admin activity should be investigated
* Correlation of multiple events provides better detection accuracy

---

## 📁 Conclusion

This lab demonstrates how monitoring administrative actions can help detect **real-world attack behavior**, especially privilege escalation and persistence. Understanding these logs is essential for effective SOC analysis.

---
