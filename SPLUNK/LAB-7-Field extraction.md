# 🔍 Splunk Lab 7 — Field Extraction

## 📌 Lab Overview
In this lab, I explored how to extract useful fields from raw log data in Splunk.  
Field extraction is an important skill for SOC analysts because raw logs often contain valuable information hidden inside unstructured text.

By extracting fields, we can turn messy log entries into searchable, filterable, and reportable security data.

---

## 🎯 Objectives
By completing this lab, I learned how to:

- Understand what fields are in Splunk
- Identify useful data inside raw logs
- Extract custom fields from event data
- Use extracted fields in searches
- Improve log visibility and investigation efficiency

---

## 🛠 Tools Used

- Splunk Enterprise

---

## 📂 Lab Environment

- Local Splunk instance
- Sample log data
- Search & Reporting App

---

## Step 1 — Search Raw Events

Started by searching all events:

```spl
index=*
````

Observed raw log entries and identified data that could be extracted.

Example values noticed:

* Username
* Source IP
* Destination IP
* Port numbers
* Status messages

---

## Step 2 — Open Field Extractor

Navigated to:

Settings → Fields → Field Extractions

OR directly from an event:

Event Actions → Extract Fields

---

## Step 3 — Select Sample Event

Selected a log event containing structured information.

Example raw event:

```text
User=admin src_ip=192.168.1.15 dest_ip=10.0.0.5 action=failed_login
```

---

## Step 4 — Extract Fields

Used Splunk’s field extractor to capture:

| Field Name | Value Example |
| ---------- | ------------- |
| user       | admin         |
| src_ip     | 192.168.1.15  |
| dest_ip    | 10.0.0.5      |
| action     | failed_login  |

Saved the extraction.

---

## Step 5 — Verify Extracted Fields

Ran search:

```spl
index=*
| table user src_ip dest_ip action
```

Confirmed that extracted fields appeared correctly.

---

## Step 6 — Analyze Extracted Data

Used extracted fields for filtering:

### Failed logins

```spl
index=* action="failed_login"
```

### Specific user

```spl
index=* user="admin"
```

### Specific source IP

```spl
index=* src_ip="192.168.1.15"
```

---

## 🔍 Key Learnings

* Raw logs contain valuable hidden information
* Field extraction makes investigations faster
* Structured fields improve search accuracy
* Custom fields help build dashboards and alerts
* Field extraction is essential for threat hunting

---

## SOC Analyst Perspective

Field extraction transforms unstructured logs into actionable intelligence.

Instead of reading raw text manually, analysts can:

✅ Filter faster
✅ Investigate smarter
✅ Build detections
✅ Create dashboards
✅ Hunt threats efficiently

---
