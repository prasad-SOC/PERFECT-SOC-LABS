# 🔍 Splunk Lab 9 — Writing Simple Queries

## 📌 Lab Overview
In this lab, I focused on writing simple search queries in Splunk.  
The goal was to move beyond basic searches and start building structured queries that help extract meaningful security data from large log datasets.

This lab is an important step toward thinking like a SOC analyst—asking the right questions and letting Splunk return the right evidence.

---

## 🎯 Objectives
By completing this lab, I learned how to:

- Write basic Splunk Search Processing Language (SPL) queries
- Search logs using keywords
- Filter events by specific fields
- Combine multiple search conditions
- Refine searches for faster investigations

---

## 🛠️ Lab Environment

- **Platform:** :contentReference[oaicite:0]{index=0}
- **Dataset:** Sample log data
- **Lab Type:** Query writing fundamentals

---

## 📚 Key Concepts Covered

### 1️⃣ Basic Search Query
Started with simple keyword searches:

```spl
error
````

This returns all events containing the word *error*.

---

### 2️⃣ Field-Based Search

Searched logs using specific fields:

```spl
host=server1
```

This filters logs generated from a specific host.

---

### 3️⃣ Combining Conditions

Used multiple conditions in one query:

```spl
host=server1 action=failed
```

This helps narrow down specific events.

---

### 4️⃣ Using OR Conditions

Searched for multiple possible values:

```spl
action=success OR action=failed
```

Useful when investigating multiple event outcomes.

---

### 5️⃣ Excluding Results

Filtered out unwanted events:

```spl
NOT status=200
```

Helpful for focusing on abnormal activity.

---

## 🔬 Investigation Steps

### Step 1

Opened Splunk Search & Reporting.

### Step 2

Loaded sample log data.

### Step 3

Executed basic keyword searches.

### Step 4

Applied field-based filtering.

### Step 5

Combined multiple search conditions.

### Step 6

Reviewed returned events and validated results.

---

## 🚀 Skills Practiced

* SPL basics
* Search optimization
* Log filtering
* Event investigation
* Analytical thinking
