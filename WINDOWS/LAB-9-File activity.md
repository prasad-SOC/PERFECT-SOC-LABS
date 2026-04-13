# 🧪 SOC Lab — File Activity Monitoring (Windows Home)

## 🎯 Objective

Understand how file operations (create, modify, delete) are logged in Windows and how to analyze them from a SOC analyst perspective.

---

## 🛠️ Lab Environment

* OS: Windows Home
* Method Used: Command Line + PowerShell (for auditing)
* Logging Enabled Using: `auditpol`

---

## ⚙️ Step 1 — Enable File Auditing (Command Line)

Since Local Security Policy is not available in Windows Home, auditing was enabled using Command Prompt.

### Command:

```cmd
auditpol /set /category:"Object Access" /success:enable /failure:enable
```

### Verify:

```cmd
auditpol /get /category:"Object Access"
```

✔ This ensures file activity events are logged in Event Viewer.

---

## 📁 Step 2 — Create Audit Folder (Command Line)

### Command:

```cmd
mkdir C:\AuditLab
```

### Verify:

```cmd
dir C:\
```

---

## 🔐 Step 3 — Enable Auditing on Folder (PowerShell)

Windows does not reliably support folder auditing via CMD, so PowerShell was used.

### Command:

```powershell
$path = "C:\AuditLab"
$acl = Get-Acl $path

$auditRule = New-Object System.Security.AccessControl.FileSystemAuditRule(
    "Everyone",
    "CreateFiles, WriteData, Delete, ReadData",
    "ContainerInherit,ObjectInherit",
    "None",
    "Success,Failure"
)

$acl.AddAuditRule($auditRule)
Set-Acl $path $acl
```

✔ This enables auditing for file access, modification, and deletion.

---

## 🧪 Step 4 — Generate File Activity (Command Line)

### Create File:

```cmd
echo hello > C:\AuditLab\test.txt
```

### Modify File:

```cmd
echo modified >> C:\AuditLab\test.txt
```

### Rename File:

```cmd
rename C:\AuditLab\test.txt test1.txt
```

### Delete File:

```cmd
del C:\AuditLab\test1.txt
```

---

## 🔍 Step 5 — Analyze Logs

### Open Event Viewer:

```cmd
eventvwr.msc
```

### Navigate:

```
Windows Logs → Security
```

### Filter Event IDs:

```
4663, 4656, 4660
```

---

## 📊 Important Event IDs

| Event ID | Description                    |
| -------- | ------------------------------ |
| 4663     | File accessed or modified      |
| 4656     | Handle requested before access |
| 4660     | File deleted                   |

---

## 🧠 Key Analysis Fields

* **Object Name** → File path
* **Process Name** → Program accessing file
* **Accesses** → Type of action (Read, Write, Delete)

---

## ⚠️ Detection Use Cases

* Unauthorized file access
* Suspicious file deletion
* Malware-like behavior (create → modify → delete)
* Activity from unusual processes (e.g., cmd.exe)

---

## 🧨 Real-World Scenario

Example attack pattern:

* Malware creates a file
* Modifies it
* Deletes it to remove traces

Logs will show:

* Multiple 4663 events (activity)
* Followed by 4660 (deletion)

---

## 🔑 Key Takeaways

* File activity logs provide direct evidence of system actions
* Attackers often leave traces through file operations
* Detection depends on correlating multiple events, not just one
* Command-line activity is especially important in real-world attacks
