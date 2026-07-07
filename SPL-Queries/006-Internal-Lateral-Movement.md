# Detection 006 - Internal Lateral Movement

## Objective

Identify hosts connecting to an unusually large number of internal systems, which may indicate lateral movement after an initial compromise.

---

## Data Source

Zeek

Log:

- conn.log

---

## SPL Query

```spl
index=zeek sourcetype=zeek:conn
| where cidrmatch("10.0.0.0/8", id.orig_h) AND cidrmatch("10.0.0.0/8", id.resp_h)
| stats dc(id.resp_h) as unique_hosts count by id.orig_h
| where unique_hosts > 10
| sort - unique_hosts
```

---

## Explanation

This query:

- Filters connections between internal hosts.
- Counts the number of unique internal destinations contacted by each source host.
- Flags systems communicating with more than 10 internal hosts.

This behavior may indicate:

- Lateral movement
- Internal reconnaissance
- Worm propagation
- Automated scanning

---

## MITRE ATT&CK

Technique:

- T1021 – Remote Services

Tactic:

- Lateral Movement

---

## Investigation Steps

1. Identify the source host.
2. Review accessed internal systems.
3. Check authentication logs.
4. Correlate with Suricata alerts.
5. Verify whether administrative activity is expected.
6. Escalate suspicious activity.
