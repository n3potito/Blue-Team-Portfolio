# Splunk Brute Force Detection Lab

## Objective

Build a basic SIEM detection workflow using Splunk and Windows Security Event Logs to identify failed authentication attempts.

## Environment

* Windows 11
* Splunk Enterprise
* Windows Security Event Logs

## Data Sources

* WinEventLog:Security
* Event ID 4624 (Successful Logon)
* Event ID 4625 (Failed Logon)

## Detection Logic

The following SPL query was used to identify failed login activity:

```spl
index=* EventCode=4625
| stats count by Failure_Reason
```

## Investigation

A failed authentication event (Event ID 4625) was investigated.

### Findings

* Host: Indio
* Event ID: 4625
* Logon Type: 2 (Interactive Logon)
* Source Network Address: 127.0.0.1
* Failure Reason: An Error occurred during Logon

## Dashboard

A Splunk dashboard was created to visualize failed login attempts over time.

## Skills Demonstrated

* SIEM Operations
* Log Analysis
* Windows Event Investigation
* SPL Query Development
* Dashboard Creation
* Security Monitoring

## Screenshots

See the screenshots folder for:

* Failed login event investigation
* Detection query results
* Splunk dashboard

## Lessons Learned

This project demonstrated how to ingest Windows Security logs into Splunk, investigate authentication failures, and create visualizations for security monitoring.
