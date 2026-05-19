# LAB 2 — User Accounts & Permissions

## Objective

Learn how Linux user accounts, groups, and file permissions work.
This lab focuses on creating users, managing groups, and controlling access to files and directories.

---

# Lab Environment

* OS: Linux (Ubuntu/Kali/CentOS)
* Access: Terminal
* Privileges: sudo/root access required

---

# Key Concepts Covered

* User accounts
* Groups
* File ownership
* Permissions
* chmod
* chown
* sudo access

---

# Step 1 — Check Current User

```bash
whoami
```

### Purpose

Displays the currently logged-in user.

### Example Output

```bash
hema
```

---

# Step 2 — View Existing Users

```bash
cat /etc/passwd
```

### Purpose

Lists all user accounts present on the system.

### What to Observe

* Username
* User ID (UID)
* Home directory
* Default shell

---

# Step 3 — Create a New User

```bash
sudo adduser analyst1
```

### Purpose

Creates a new user account named `analyst1`.

### During Setup

You may be asked to:

* Set a password
* Enter optional details

---

# Step 4 — Switch to the New User

```bash
su - analyst1
```

### Purpose

Switches the terminal session to the new user account.

### Verify

```bash
whoami
```

Expected Output:

```bash
analyst1
```

---

# Step 5 — Check User ID Information

```bash
id
```

### Purpose

Displays:

* UID
* GID
* Group memberships

### Example Output

```bash
uid=1001(analyst1) gid=1001(analyst1)
```

---

# Step 6 — Create a Group

Switch back to the main sudo user first.

```bash
exit
```

Now create a group:

```bash
sudo groupadd socteam
```

### Purpose

Creates a new group named `socteam`.

---

# Step 7 — Add User to Group

```bash
sudo usermod -aG socteam analyst1
```

### Purpose

Adds `analyst1` to the `socteam` group.

### Verify Group Membership

```bash
groups analyst1
```

Expected Output:

```bash
analyst1 : analyst1 socteam
```

---

# Step 8 — Create a Test File

```bash
touch investigation.txt
```

### Purpose

Creates an empty file for permission testing.

---

# Step 9 — Check File Permissions

```bash
ls -l investigation.txt
```

### Example Output

```bash
-rw-r--r-- 1 hema hema 0 May 19 10:00 investigation.txt
```

---

# Understanding Permissions

```text
-rw-r--r--
```

| Symbol | Meaning            |
| ------ | ------------------ |
| rw-    | Owner permissions  |
| r--    | Group permissions  |
| r--    | Others permissions |

### Permission Meanings

| Symbol | Access  |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

---

# Step 10 — Modify Permissions

## Give Execute Permission

```bash
chmod +x investigation.txt
```

Check again:

```bash
ls -l investigation.txt
```

Expected Output:

```bash
-rwxr-xr-x
```

---

# Step 11 — Change File Ownership

```bash
sudo chown analyst1:socteam investigation.txt
```

### Purpose

Changes:

* Owner → analyst1
* Group → socteam

Verify:

```bash
ls -l investigation.txt
```

---

# Step 12 — Test File Access

Switch user:

```bash
su - analyst1
```

Try editing the file:

```bash
echo "SOC Investigation Started" >> investigation.txt
```

Display contents:

```bash
cat investigation.txt
```

Expected Output:

```bash
SOC Investigation Started
```

---

# Step 13 — Remove Write Permission

```bash
chmod u-w investigation.txt
```

### Purpose

Removes write access from the owner.

Verify:

```bash
ls -l investigation.txt
```

Try writing again:

```bash
echo "Test Entry" >> investigation.txt
```

### Expected Result

Permission denied error.

---

# Important Commands Summary

| Command  | Purpose             |
| -------- | ------------------- |
| whoami   | Current user        |
| id       | User and group info |
| adduser  | Create user         |
| groupadd | Create group        |
| usermod  | Modify user groups  |
| chmod    | Change permissions  |
| chown    | Change ownership    |
| ls -l    | View permissions    |

---

# Skills Learned

By completing this lab, you practiced:

* Creating Linux users
* Managing groups
* Understanding Linux permissions
* Changing ownership
* Restricting file access
* Performing basic Linux administration tasks

---

# Real-World SOC Relevance

SOC analysts often work on Linux systems where permissions and user management are critical for:

* Log protection
* Access control
* Investigation integrity
* Secure administration
* Threat containment

Understanding permissions helps analysts identify:

* Unauthorized access
* Misconfigured systems
* Privilege escalation risks

---

# Lab Completion Checklist

* [x] Viewed system users
* [x] Created a new user
* [x] Created a group
* [x] Added user to group
* [x] Checked file permissions
* [x] Modified permissions
* [x] Changed ownership
* [x] Tested access restrictions

---

# Conclusion

This lab introduced the fundamentals of Linux user management and file permissions.
These concepts form the foundation of Linux security administration and are essential skills for SOC analysts and cybersecurity professionals.
