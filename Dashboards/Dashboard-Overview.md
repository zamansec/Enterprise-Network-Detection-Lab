# Splunk Dashboard Overview

## Purpose

The Splunk dashboards provide a centralized view of network activity, IDS alerts, and security events collected from Zeek and Suricata.

The dashboards help SOC analysts quickly identify abnormal behavior, investigate incidents, and monitor the security posture of the monitored environment.

---

# Dashboards

## 1. Network Activity Dashboard

Data Source:

- Zeek

Purpose:

- Monitor network connections
- Top source IPs
- Top destination IPs
- Network protocols
- Traffic trends

---

## 2. DNS Monitoring Dashboard

Data Source:

- Zeek DNS Logs

Purpose:

- DNS request volume
- Top queried domains
- Top clients
- Suspicious DNS activity

---

## 3. HTTP Monitoring Dashboard

Data Source:

- Zeek HTTP Logs

Purpose:

- HTTP requests
- User-Agent analysis
- Top websites
- Suspicious HTTP activity

---

## 4. IDS Alert Dashboard

Data Source:

- Suricata

Purpose:

- Alert trends
- Alert severity
- Top signatures
- Alert categories

---

## 5. Detection Dashboard

Purpose:

Display results from enterprise SPL detections including:

- Port Scanning
- DNS Tunneling
- Beaconing
- Large Data Transfer
- Lateral Movement
- Suspicious HTTP User-Agent

---

# SOC Workflow

SOC Analyst

↓

Review Dashboard

↓

Investigate Alert

↓

Run SPL Queries

↓

Validate Threat

↓

Respond
