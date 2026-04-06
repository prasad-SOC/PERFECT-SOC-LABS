# Windows Lab 2: Login Success & Failure Monitoring

## Objective
Analyze Windows Security logs to identify and understand successful and failed login attempts.

---

## Lab Environment
- Operating System: Windows 10 / 11
- Tool Used: Event Viewer
- Log Source: Windows Security Logs

---

## Skills Covered
- Event log analysis
- Log filtering
- Authentication monitoring
- Basic threat detection

---

## Key Event IDs
- 4624 → Successful Logon
- 4625 → Failed Logon
- 4798 → User group membership enumeration

---

## Tasks

### 1. Access Security Logs
- Open Event Viewer  
- Navigate to:  
  `Windows Logs → Security`

---

### 2. Identify Login Events
- Locate authentication-related logs  
- Identify Event IDs for:
  - Successful logins
  - Failed login attempts

---

### 3. Filter Failed Login Attempts
- Use "Filter Current Log"  
- Enter Event ID for failed logins  
- Review multiple entries

---

### 4. Analyze Failed Login Details
For each failed login, examine:
- Account Name  
- Source IP / Workstation Name  
- Logon Type  
- Failure Reason  

---

### 5. Filter Successful Logins
- Apply filter for successful login Event ID  
- Observe login activity

---

### 6. Compare Login Activity
- Compare successful vs failed logins  
- Identify patterns in:
  - Frequency  
  - Accounts targeted  
  - Time of occurrence  

---

### 7. Detect Suspicious Behavior
Check for:
- Multiple failed attempts on a single account  
- Rapid login attempts  
- Unusual login times  
- Unknown sources  

---

### 8. Analyze Logon Types
- Identify logon types in events  
- Understand their purpose (local, remote, service, etc.)

---

### 9. Perform Timeline Analysis
- Select a time window  
- Observe sequence of events:
  - Failed → Successful (if applicable)

---

### 10. Document Findings
Record:
- Observed Event IDs  
- Login patterns  
- Any anomalies  
- Key observations  

---

## Outcome
By completing this lab, you will:
- Understand how authentication events are logged in Windows  
- Gain experience filtering and analyzing security logs  
- Develop a basic detection mindset for login-related threats  

---

## Notes
- In a single-system lab environment, log volume may be limited  
- Real-world environments will contain significantly more data and complexity  

---
