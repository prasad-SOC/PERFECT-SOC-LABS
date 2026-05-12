# Splunk Lab 6 — Alerts & Dashboards

## Objective
In this lab, I learned how Security Analysts use alerts and dashboards in Splunk to move from passive log searching to active monitoring.

The goal was to:
- Create scheduled alerts
- Define trigger conditions
- Configure alert actions
- Build visual dashboards
- Monitor suspicious activity in real-time

---

## Lab Environment
Tool Used:
- Splunk Enterprise

Data Source:
- Sample security/event logs

Lab Type:
- Detection Engineering / Monitoring

---

## Skills Practiced
✅ Creating search-based alerts  
✅ Setting trigger conditions  
✅ Configuring alert frequency  
✅ Understanding real-time vs scheduled alerts  
✅ Building visual dashboards  
✅ Using charts and panels for security monitoring  

---

## Step 1 — Launch Splunk
Open Splunk Enterprise and log in.

Navigate to:

Search & Reporting

---

## Step 2 — Create an Alert

Use a search query such as:

index=* "failed"

This searches for failed events.

Click:

Save As → Alert

Configure:

Name:
Failed Login Detection

Alert Type:
Scheduled

Time Range:
Last 15 minutes

Trigger Condition:
Number of Results > 5

Trigger:
Once

Click Save.

---

## Step 3 — Test the Alert

Generate sample failed events.

Run the search again and verify:
- Alert triggers
- Trigger count increases
- Alert appears in triggered alerts

Navigate to:

Activity → Triggered Alerts

---

## Step 4 — Create a Dashboard

Run a search:

index=*

Click:

Visualization

Select:
- Bar Chart
- Pie Chart
- Line Chart

Click:

Save As → Dashboard

Dashboard Name:

SOC Monitoring Dashboard

---

## Step 5 — Add Panels

Added multiple panels such as:

### Failed Login Events
Search:

index=* "failed"

### Events by Host
Search:

index=* | stats count by host

### Events by Source
Search:

index=* | stats count by source

---

## Observations

- Alerts help detect suspicious activity automatically.
- Dashboards make large volumes of logs easier to understand.
- Visualization improves investigation speed.
- Scheduled monitoring reduces manual effort.

---

## Key Learning

Searching logs finds events.

Alerts notify analysts.

Dashboards help analysts see trends.

Together, they form the foundation of proactive monitoring.

---

## Outcome

Successfully created:
✅ Security alerts  
✅ Scheduled detections  
✅ Visual dashboards  
✅ Monitoring panels  

This lab helped me understand how SOC analysts monitor environments in real-time.
