# Enterprise Network Security Monitoring (NSM) Architecture

## Overview

This project simulates an enterprise Network Security Monitoring (NSM) environment using Splunk Enterprise, Zeek, and Suricata.

The architecture demonstrates how network telemetry is collected, analyzed, and visualized within a Security Operations Center (SOC). The lab follows enterprise monitoring principles while remaining lightweight enough to run in a virtual environment.

---

# Objectives

- Capture network traffic
- Generate network metadata
- Detect suspicious activity
- Centralize logs in Splunk
- Enable security investigations
- Support threat hunting and detection engineering

---

# Environment

## Host System

- Windows 11

## Monitoring Server

- Ubuntu Virtual Machine

Installed Components:

- Splunk Enterprise
- Zeek
- Suricata
- Git

---

# Components

## Splunk Enterprise

Role:

Security Information and Event Management (SIEM)

Responsibilities:

- Collect security logs
- Index data
- Execute SPL searches
- Display dashboards
- Support investigations

---

## Zeek

Role:

Network Security Monitoring (NSM)

Responsibilities:

- Analyze network traffic
- Generate protocol metadata
- Record DNS activity
- Record HTTP activity
- Record SSL/TLS activity
- Produce connection logs

Example Logs:

- conn.log
- dns.log
- http.log
- ssl.log
- notice.log
- files.log

---

## Suricata

Role:

Intrusion Detection System (IDS)

Responsibilities:

- Inspect packets
- Detect malicious traffic
- Generate alerts
- Produce JSON security events

Primary Log:

- eve.json

---

# Data Flow

Network Traffic

↓

Zeek

↓

Suricata

↓

Security Logs

↓

Splunk Enterprise

↓

Dashboards

↓

SPL Searches

↓

SOC Investigation

---

# Current Data Sources

| Source | Status |
|----------|--------|
| Zeek | Operational |
| Suricata | Operational |
| Windows Endpoint | Planned |

---

# Future Enhancements

- Windows Endpoint Integration
- Sysmon
- Splunk Universal Forwarder
- Atomic Red Team
- Sigma Rules
- MITRE ATT&CK Mapping
- Wazuh Integration
- SOAR Automation

---

# Enterprise SOC Mapping

| Component | Enterprise Function |
|------------|--------------------|
| Zeek | Network Telemetry |
| Suricata | Intrusion Detection |
| Splunk | SIEM |
| SPL | Detection Engineering |
| Dashboards | SOC Monitoring |

---

# Key Skills Demonstrated

- Network Security Monitoring
- SIEM Operations
- IDS Monitoring
- Detection Engineering
- Threat Hunting
- Incident Investigation
- Enterprise Documentation
