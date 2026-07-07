# Installation Guide

## Overview

This document describes how to deploy the Enterprise Network Detection Lab on Ubuntu.

The lab is designed to simulate an enterprise Network Security Monitoring (NSM) environment using Splunk Enterprise, Zeek, and Suricata.

---

# Environment

## Host

- Windows 11

## Virtual Machine

- Ubuntu Linux

---

# Software Components

| Component | Purpose |
|----------|---------|
| Splunk Enterprise | Security Information and Event Management (SIEM) |
| Zeek | Network Security Monitoring |
| Suricata | Intrusion Detection System |
| Git | Version Control |

---

# Prerequisites

Before installation, ensure:

- Ubuntu VM is installed
- Internet connectivity is available
- Administrative (sudo) access
- Git is installed

---

# Installation Order

Install components in the following order:

1. Git
2. Splunk Enterprise
3. Zeek
4. Suricata

---

# Splunk Enterprise

Status:

- Installed
- Operational
- Accessible through the web interface

Purpose:

- Centralize logs
- Search events
- Create dashboards
- Perform investigations

---

# Zeek

Status:

- Installed
- Operational

Purpose:

- Analyze network traffic
- Generate protocol logs
- Produce metadata for investigations

Example Logs:

- conn.log
- dns.log
- http.log
- ssl.log

---

# Suricata

Status:

- Installed
- Operational

Purpose:

- Inspect packets
- Detect threats
- Generate IDS alerts

Primary Log:

- eve.json

---

# Log Ingestion

Current Sources:

- Zeek
- Suricata

Destination:

- Splunk Enterprise

---

# Verification

Confirm the following:

- Splunk Web is accessible
- Zeek is generating logs
- Suricata is generating eve.json
- Splunk is indexing both log sources

---

# Future Enhancements

The following components will be added in Phase 2:

- Windows Endpoint
- Sysmon
- Splunk Universal Forwarder
- Atomic Red Team
- MITRE ATT&CK Mapping
- Sigma Rules
- Wazuh
- SOAR Integration

---

# Skills Demonstrated

- Ubuntu Administration
- SIEM Deployment
- IDS Deployment
- Network Security Monitoring
- Enterprise Documentation
