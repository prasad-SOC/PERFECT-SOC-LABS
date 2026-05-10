# Splunk Lab 4 – Detect Failed Logins

## 🎯 Objective
In this lab, I learned how to detect failed login attempts using Splunk.  
Failed login detection is one of the most important use cases in Security Operations because repeated authentication failures may indicate:

- Brute-force attacks
- Password spraying
- Unauthorized access attempts
- Misconfigured services
- User credential issues

This lab focused on identifying failed authentication events, filtering relevant logs, and analyzing suspicious login behavior.

---

# 🛠 Lab Environment

## Tool Used
- Splunk Enterprise

## Data Source
- Authentication / Security logs

## Skills Practiced
- Searching authentication events
- Filtering failed logins
- Field extraction
- Event analysis
- Security investigation

---

# Step 1 – Open Splunk Search & Reporting

Logged into Splunk and opened:

Apps → Search & Reporting

This is where all log investigations begin.

---

# Step 2 – Search Authentication Logs

Started by searching authentication-related logs:

```spl
login
````

This displayed all login-related events available in the dataset.

---

# Step 3 – Filter Failed Login Events

Next, filtered specifically for failed authentication attempts:

```spl
login failed
```

This reduced noise and showed only failed login events.

---

# Step 4 – Analyze Event Details

Examined important fields such as:

* Username
* Source IP
* Host
* Timestamp
* Failure reason

Questions investigated:

* Which users failed authentication?
* How many failures occurred?
* Were failures coming from the same IP?
* Were multiple accounts targeted?

---

# Step 5 – Count Failed Attempts

Used Splunk statistics to identify repeated failures:

```spl
"login failed" | stats count by user
```

This showed how many failed attempts each user had.

---

# Step 6 – Identify Source IP Activity

Investigated where failed attempts originated:

```spl
"login failed" | stats count by src_ip
```

This helped identify suspicious IP addresses.

---

# Step 7 – Detect Potential Brute Force Activity

Looked for patterns such as:

* Multiple failures in short time
* Same IP targeting multiple users
* Single user with repeated failures

These patterns may indicate brute-force or password spraying attacks.

---

# Key Learnings

✅ How to search authentication logs
✅ How to isolate failed login events
✅ How to analyze usernames and source IPs
✅ How to count repeated failures
✅ How SOC analysts detect brute-force behavior

---

# Why This Matters in SOC

Failed login detection is an essential security monitoring use case.

SOC analysts use this technique to:

* Detect credential attacks
* Identify compromised accounts
* Investigate unauthorized access attempts
* Escalate security incidents quickly
