# 🧪 Windows Registry Basics Lab

## 🎯 Objective

Learn the fundamentals of the Windows Registry, how to navigate it, and understand its importance in security monitoring and threat detection.

---

## 🧠 Overview

The Windows Registry is a hierarchical database that stores:

* Operating system configurations
* User preferences
* Application settings
* Startup behaviors

### 🔐 Why It Matters (SOC Perspective)

* Used by attackers for **persistence**
* Stores critical system and user activity data
* Valuable for **incident response and forensic analysis**

---

## 🧰 Lab Requirements

* Windows system (Virtual Machine recommended)
* Administrator access
* Registry Editor (`regedit`)

---

## 🔍 Lab Steps

### Step 1 — Open Registry Editor

1. Press `Win + R`
2. Type `regedit`
3. Press Enter
4. Accept UAC prompt (if shown)

---

### Step 2 — Understand Registry Structure

The registry consists of five main hives:

| Hive                       | Description            |
| -------------------------- | ---------------------- |
| HKEY_LOCAL_MACHINE (HKLM)  | System-wide settings   |
| HKEY_CURRENT_USER (HKCU)   | Current user settings  |
| HKEY_CLASSES_ROOT (HKCR)   | File associations      |
| HKEY_USERS (HKU)           | All user profiles      |
| HKEY_CURRENT_CONFIG (HKCC) | Hardware configuration |

**Structure Hierarchy:**

```
Hive → Key → Subkey → Value
```

---

### Step 3 — Explore Important Registry Paths

#### 🔹 Startup Programs (Critical for Persistence)

```
HKLM\Software\Microsoft\Windows\CurrentVersion\Run
HKCU\Software\Microsoft\Windows\CurrentVersion\Run
```

#### 🔹 Installed Programs

```
HKLM\Software\Microsoft\Windows\CurrentVersion\Uninstall
```

#### 🔹 User Activity / Explorer Settings

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer
```

---

### Step 4 — Create a Test Registry Entry

1. Navigate to:

```
HKCU\Software
```

2. Right-click → **New → Key**

   * Name: `TestLab`

3. Inside `TestLab`:

   * Right-click → **New → String Value**
   * Name: `Demo`
   * Value: `SOC_Lab`

---

### Step 5 — Verify Changes

* Close Registry Editor
* Reopen and navigate back to:

```
HKCU\Software\TestLab
```

* Confirm the key and value exist

---

### Step 6 — Delete Test Entry

* Right-click `TestLab`
* Click **Delete**

---

## 🔐 Security Relevance

### 🧨 Common Persistence Technique

Attackers often use:

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Run
```

To execute malicious programs at user login.

---

### 🔎 Indicators of Suspicious Activity

* Unknown or random executable names
* Entries pointing to unusual paths:

  * `C:\Users\Public\`
  * `AppData\Local\Temp\`
* Obfuscated or non-human-readable names

---

### 🛡️ Example Scenario

**Observation:**
System slows down after login

**Investigation:**

* Checked Run key entries
* Found unknown executable in a public directory

**Conclusion:**
Possible persistence mechanism used by malware

---

## ✅ Lab Checklist

* [ ] Opened Registry Editor
* [ ] Understood registry structure
* [ ] Explored important hives
* [ ] Navigated startup registry paths
* [ ] Created a test key and value
* [ ] Verified registry changes
* [ ] Deleted test entry

---

## 🧠 Key Takeaways

### ✔ Facts

* Registry stores critical system and user configurations
* Startup keys control automatic execution
* Changes persist across system reboots

### ✔ Analyst Insights

* Registry is a key source for detecting persistence
* Small entries can have major impact
* Always validate unknown startup entries

---

## ⚠️ Safety Notes

* Avoid modifying unknown registry keys
* Use a virtual machine for practice
* Incorrect changes can impact system stability

---

## 📊 Confidence Level

**High** — Based on standard Windows architecture and common security practices.

---
