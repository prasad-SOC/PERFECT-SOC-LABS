# Splunk Lab 2: Filtering Events

## Objective
Learn how to filter specific events in Splunk using search terms, fields, and operators.

## Lab Environment
- Tool: Splunk Enterprise
- Data Source: Sample logs / generated logs
- Focus Area: Event filtering and narrowing down search results

---

## Step 1: Launch Splunk
Open Splunk in your browser and log in.

Example:
http://localhost:8000

---

## Step 2: Open Search & Reporting
Navigate to:

Apps → Search & Reporting

This is where event searches are performed.

---

## Step 3: View All Events
Run:

index=main

This shows all available events from the main index.

Observation:
A large number of logs are displayed.

---

## Step 4: Filter by Keyword
Search for a specific keyword:

index=main error

Purpose:
Shows only events containing "error".

Observation:
Only relevant error-related logs remain.

---

## Step 5: Filter by Host
Search:

index=main host=<your-hostname>

Purpose:
View logs from one specific system.

---

## Step 6: Filter by Source
Search:

index=main source="*syslog*"

Purpose:
Display only syslog events.

---

## Step 7: Filter by Severity
Search:

index=main log_level=ERROR

Purpose:
Locate critical events quickly.

---

## Step 8: Combine Filters
Search:

index=main error host=<your-hostname>

Purpose:
Narrow results further.

---

## Skills Learned
- Basic filtering
- Keyword searches
- Field-based filtering
- Combining search conditions
- Faster investigation workflow

## Conclusion
This lab introduced event filtering in Splunk. Instead of searching all logs manually, filters help analysts quickly isolate relevant security events.
