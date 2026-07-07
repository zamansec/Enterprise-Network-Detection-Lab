# Detection 001 - Port Scan Detection

## Objective

Detect hosts attempting to connect to a large number of destination ports within a short period of time.

---

## Data Source

Zeek

Log:

- conn.log

---

## SPL Query

```spl
index=zeek sourcetype=zeek:conn
| stats dc(id.resp_p) as unique_ports count by id.orig_h
| where unique_ports > 20
| sort - unique_ports
```

---

## Explanation

This query:

- Counts the number of unique destination ports contacted by each source IP.
- Flags hosts communicating with more than 20 unique ports.
- Helps identify reconnaissance and port-scanning activity.

---

## MITRE ATT&CK

Technique:

- T1046 – Network Service Discovery

Tactic:

- Discovery

---

## Expected Investigation

When this detection triggers:

1. Review the source IP.
2. Check the destination systems.
3. Determine whether the activity is authorized.
4. Investigate for additional reconnaissance activity.
5. Escalate if malicious behavior is confirmed.
