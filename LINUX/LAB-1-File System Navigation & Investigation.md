# 🐧 Linux Lab 1 — File System Navigation & Investigation

## 📌 Objective
The goal of this lab is to understand how Linux organizes files and directories, and to practice navigating the file system like a SOC analyst or system administrator.

This lab focuses on exploring directories, identifying important system locations, and investigating files using native Linux commands.

---

## 🧠 Skills Learned

- Understanding Linux file system structure
- Navigating directories efficiently
- Listing and analyzing files
- Viewing hidden files
- Finding current working directory
- Investigating file permissions and metadata
- Using absolute and relative paths

---

## 🛠️ Tools Used

- Linux Terminal
- Bash Shell

---

## 📂 Lab Environment

- Operating System: Ubuntu Linux *(or Kali Linux)*
- User Shell: Bash

---

## 📖 Key Linux Directories Explored

| Directory | Purpose |
|-----------|---------|
| / | Root directory |
| /home | User directories |
| /etc | Configuration files |
| /var | Logs and variable data |
| /tmp | Temporary files |
| /usr | User applications |
| /bin | Essential commands |
| /proc | Process information |

---

## 🔬 Lab Tasks

### Task 1 — Check Current Directory

```bash
pwd
````

**Purpose:**
Displays the present working directory.

---

### Task 2 — List Files and Directories

```bash
ls
```

**Purpose:**
Lists files in current directory.

---

### Task 3 — View Detailed File Information

```bash
ls -l
```

**Purpose:**
Displays permissions, owner, size, and modification dates.

---

### Task 4 — View Hidden Files

```bash
ls -la
```

**Purpose:**
Shows hidden files and directories.

---

### Task 5 — Change Directory

```bash
cd /home
```

**Purpose:**
Moves into another directory.

---

### Task 6 — Move Back One Directory

```bash
cd ..
```

**Purpose:**
Moves one level up.

---

### Task 7 — Move to Home Directory

```bash
cd ~
```

**Purpose:**
Returns to the user's home directory.

---

### Task 8 — Investigate File Type

```bash
file example.txt
```

**Purpose:**
Identifies file type.

---

### Task 9 — View File Metadata

```bash
stat example.txt
```

**Purpose:**
Displays detailed file information.

---

### Task 10 — Read Directory Contents Clearly

```bash
tree
```

**Purpose:**
Visualizes directory structure.

> Install if missing:

```bash
sudo apt install tree
```

---

## 🔍 Investigation Scenario

During this lab, I explored system directories to understand where:

* User data is stored
* Configuration files exist
* Logs are generated
* Temporary files are created
* Executable binaries are located

This knowledge is essential for incident response and forensic investigations.

---
## 🎯 Key Takeaways

✅ Linux uses a hierarchical file system
✅ Every file has permissions and metadata
✅ Hidden files often store important configurations
✅ Logs and system artifacts are spread across multiple directories
✅ File system knowledge is critical for SOC investigations
