# 🧪 PowerShell Logging Analysis Lab

## 🎯 Objective

Enable and analyze PowerShell logging to observe command execution and identify suspicious activity.

---

## 🧰 Requirements

* Windows system (Home/Pro/Enterprise)
* Administrator access
* PowerShell
* Event Viewer

---

## ⚙️ Lab Setup (Windows Home Method - Registry)

### Step 1: Open Registry Editor

* Press `Win + R`
* Type `regedit`
* Press Enter

### Step 2: Navigate to Path

```
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\PowerShell
```

> If the `PowerShell` key does not exist, create it.

### Step 3: Enable Script Block Logging

* Create Key: `ScriptBlockLogging`
* Inside it, create DWORD:

  ```
  EnableScriptBlockLogging = 1
  ```

### Step 4: Enable Module Logging

* Create Key: `ModuleLogging`
* Inside it, create DWORD:

  ```
  EnableModuleLogging = 1
  ```

### Step 5: Configure Module Names

* Inside `ModuleLogging`, create Key:

  ```
  ModuleNames
  ```
* Inside `ModuleNames`, create String:

  ```
  Name: *
  Value: *
  ```

### Step 6: Restart System

* Restart the system to apply changes

---

## 🔬 Execution Phase

### Step 7: Generate Normal Activity

Run in PowerShell:

```
Get-Process
Get-Service
whoami
```

### Step 8: Generate Suspicious Activity

```
Invoke-Expression "Get-Date"
```

### Step 9: Generate Encoded Command

```
powershell -enc RwBlAHQALQBEAGEAdABlAA==
```

---

## 🔍 Log Analysis

### Step 10: Open Event Viewer

* Press `Win + R`
* Type `eventvwr`

### Step 11: Navigate to Logs

```
Applications and Services Logs
→ Microsoft
→ Windows
→ PowerShell
→ Operational
```

### Step 12: Identify Key Events

| Event ID | Description          |
| -------- | -------------------- |
| 4103     | Module Logging       |
| 4104     | Script Block Logging |
| 400      | Engine Start         |
| 403      | Engine Stop          |

---

## 🔎 Investigation Tasks

* Identify all executed commands
* Locate Event ID 4104 logs
* Detect encoded commands
* Check for use of:

  * Invoke-Expression (IEX)
* Compare normal vs suspicious activity

---

## 🚨 Detection Focus

* Encoded commands (`-enc`)
* Obfuscated scripts
* Suspicious keywords (`IEX`)
* Unusual execution patterns

---

## ✅ Validation Checklist

* [ ] Script Block Logging enabled
* [ ] Module Logging enabled
* [ ] System restarted
* [ ] Commands executed
* [ ] Logs visible in Event Viewer
* [ ] Event ID 4104 contains script content

---

## 📌 Expected Outcome

* Visibility into PowerShell command execution
* Ability to detect suspicious activity
* Understanding of how attackers abuse PowerShell

---

## 🧠 Key Learning

* PowerShell logging reveals actual executed code
* Script Block Logging is critical for detection
* Logs can be used to reconstruct attacker behavior
