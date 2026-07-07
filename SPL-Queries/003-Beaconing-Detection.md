# Detection 003 - Beaconing Detection

## Objective

Identify systems repeatedly communicating with the same destination, which may indicate malware beaconing or command-and-control (C2) activity.

---

## Data Source

Zeek

Log:

- conn.log

---

## SPL Query

```spl
index=zeek sourcetype=zeek:conn
| stats count by id.orig_h id.resp_h
| where count > 50
| sort - count
```

---

## Explanation

This query:

- Counts the number of connections between each source and destination IP pair.
- Highlights hosts that repeatedly communicate with the same destination.
- Frequent, repetitive communication may indicate beaconing or persistent command-and-control traffic.

---

## MITRE ATT&CK

Technique:

- T1071 – Application Layer Protocol

Tactic:

- Command and Control

---

## Investigation Steps

1. Identify the source host.
2. Review the destination IP.
3. Check the connection frequency and timing.
4. Determine whether the destination is known or trusted.
5. Correlate with DNS, HTTP, and Suricata alerts.
6. Escalate if malicious behavior is confirmed.
