# Splunk Lab 3 — Time-Based Analysis

## Overview
This lab focuses on performing time-based analysis in Splunk. Time is one of the most critical elements in security investigations because suspicious activity often becomes visible only when events are analyzed over minutes, hours, or days.

In this lab, I explored how to filter logs using time ranges, visualize event activity over time, and identify patterns using Splunk's built-in time analysis commands.

---

## Lab Objectives

- Understand the importance of time-based analysis
- Learn how to use Splunk's time picker
- Search events within specific time ranges
- Create timelines using `timechart`
- Group events into hourly intervals
- Compare activity across multiple log sources

---

## Lab Setup

### Requirements

- Splunk Enterprise installed locally
- Sample logs ingested into Splunk
- Search & Reporting app enabled

---

## Step 1: Launch Splunk

Open Splunk in your browser:

`http://localhost:8000`

Log in and open:

**Apps → Search & Reporting**

---

## Step 2: Explore the Time Picker

At the top-right corner of Splunk, locate the **Time Range Picker**.

Practice switching between:

- Last 15 minutes
- Last 60 minutes
- Last 24 hours
- Last 7 days
- Custom range

Observe how the event count changes.

---

## Step 3: Search All Events

Run:

```spl
index=*
```

This displays all available events.

---

## Step 4: Search Events from Last 24 Hours

Run:

```spl
index=* earliest=-24h
```

### Explanation

- `earliest=-24h` → Shows events from the last 24 hours

---

## Step 5: Create a Timeline

Run:

```spl
index=* | timechart count
```

### Explanation

- `timechart` creates a time-based graph
- `count` shows number of events over time

---

## Step 6: Compare Different Log Sources

Run:

```spl
index=* | timechart count by sourcetype
```

### Explanation

This helps identify:

- Which log sources are most active
- Sudden spikes in specific log types
- Unusual behavior over time

---

## Step 7: Hourly Analysis

Run:

```spl
index=* | bucket _time span=1h | stats count by _time
```

### Explanation

- `bucket` groups timestamps into 1-hour intervals
- `stats count` counts events per hour

---

## Key Observations

During this lab, I observed:

- Event counts change significantly across time ranges
- Some log sources generate more events than others
- Timeline visualization makes spikes easier to detect
- Hourly grouping helps identify active periods

---

## Skills Gained

- Splunk time filtering
- Timeline analysis
- Event trend visualization
- Hourly event grouping
- Log source comparison

---

## Commands Used

```spl
index=*
```

```spl
index=* earliest=-24h
```

```spl
index=* | timechart count
```

```spl
index=* | timechart count by sourcetype
```

```spl
index=* | bucket _time span=1h | stats count by _time
```

---

## Key Takeaway

Time-based analysis is essential in SOC investigations because attacks often reveal themselves through patterns, spikes, and anomalies over time.

Understanding how to analyze logs chronologically is a core skill for every SOC analyst.
