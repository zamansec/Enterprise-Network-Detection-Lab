# Detection 005 - Large Data Transfer

## Objective

Identify hosts transferring unusually large amounts of data, which may indicate data exfiltration or unauthorized file transfers.

---

## Data Source

Zeek

Log:

- conn.log

---

## SPL Query

```spl
index=zeek sourcetype=zeek:conn
| eval total_bytes=orig_bytes+resp_bytes
| where total_bytes > 100000000
| table _time id.orig_h id.resp_h proto service orig_bytes resp_bytes total_bytes
| sort - total_bytes
```

---

## Explanation

This query:

- Calculates the total bytes exchanged during a connection.
- Flags connections transferring more than 100 MB.
- Highlights sessions that may require further investigation.

> **Note:** The 100 MB threshold is an example for a lab environment. In production, thresholds should be based on normal network behavior.

---

## MITRE ATT&CK

Technique:

- T1041 – Exfiltration Over C2 Channel

Tactic:

- Exfiltration

---

## Investigation Steps

1. Identify the source host.
2. Verify whether the destination is trusted.
3. Determine the application or protocol used.
4. Review user activity during the transfer.
5. Correlate with DNS, HTTP, and IDS alerts.
6. Confirm whether the transfer was authorized.
