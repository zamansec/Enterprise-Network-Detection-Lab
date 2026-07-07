# Detection 008 - Top Suricata Signatures

## Objective

Identify the most frequently triggered Suricata IDS signatures to understand attack trends and prioritize investigations.

---

## Data Source

Suricata

Log:

- eve.json

---

## SPL Query

```spl
index=suricata sourcetype=suricata event_type=alert
| stats count by alert.signature alert.category
| sort - count
```

---

## Explanation

This query:

- Counts the number of occurrences for each Suricata signature.
- Groups alerts by signature and category.
- Sorts results by frequency.

This helps analysts quickly identify:

- Frequently targeted services
- Recurring attack techniques
- Noisy IDS rules
- Emerging attack patterns

---

## MITRE ATT&CK

The ATT&CK mapping depends on the individual signature that triggered the alert.

---

## Investigation Steps

1. Review the most frequent signatures.
2. Identify affected assets.
3. Determine whether the activity is expected.
4. Correlate with Zeek logs.
5. Tune noisy signatures if necessary.
6. Escalate confirmed malicious activity.
