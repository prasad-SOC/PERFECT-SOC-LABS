# 🧪 Lab 1 — Windows Event Viewer Basics

## 🎯 Objective
Learn how to navigate Windows Event Viewer and analyze basic authentication events from Security logs.

## 🛠️ Tool Required
- Windows OS
- Event Viewer

---

## 🚀 Lab Instructions

### Step 1 — Open Event Viewer
- Press `Win + R`
- Type `eventvwr`
- Launch the application

---

### Step 2 — Explore Log Categories
- Navigate to: Event Viewer → Windows Logs
- Identify available log types:
  - Application  
  - Security  
  - System  
  - Setup  
  - Forwarded Events  

---

### Step 3 — Access Security Logs
- Click on **Security**
- Observe the list of events
- Identify key columns such as:
  - Event ID  
  - Level  
  - Date and Time  
  - Task Category  

---

### Step 4 — Analyze an Event
- Select any event from the list
- Review the following:
  - Event ID  
  - Description (General tab)  
  - Additional details (Details tab)  

---

### Step 5 — Filter Important Events
- Use **Filter Current Log**
- Search for:
  - Event ID `4624`
  - Event ID `4625`

---

### Step 6 — Compare Events
- Identify differences between:
  - Successful login events  
  - Failed login events  

- Observe:
  - Frequency of events  
  - Time patterns  
  - Account details  
  - Source Network Address (if available)  

---

### Step 7 — Explore System Logs
- Navigate to **System**
- Review different types of system events such as:
  - Errors  
  - Warnings  
  - Informational events  

---

## 🧠 Tasks

Answer the following:

1. What is the purpose of Event Viewer?  
2. Which log is most important for authentication monitoring?  
3. What does Event ID 4624 represent?  
4. What does Event ID 4625 represent?  
5. What differences can you observe between successful and failed login events?  
6. What does the Source Network Address indicate?  

---

## ✅ Completion Criteria

You should be able to:
- Navigate Event Viewer confidently  
- Identify key log categories  
- Filter and locate specific Event IDs  
- Perform basic comparison of authentication events  

---

## 📌 Notes
- Do not assume all failed logins are attacks  
- Focus on patterns and frequency rather than individual events  
