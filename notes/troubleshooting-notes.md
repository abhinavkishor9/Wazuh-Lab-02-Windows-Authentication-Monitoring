# Troubleshooting Notes

## Issue: No Authentication Events Returned

### Symptom

Searches for:

```text
win.system.eventID:4624
```

or

```text
win.system.eventID:4625
```

returned no results.

### Checks Performed

- Verified Wazuh Agent status
- Verified agent communication
- Verified endpoint was active

### Resolution

Generated new authentication activity and waited for ingestion.

---

## Issue: Agent Not Reporting

### Symptom

Agent status displayed:

```text
Disconnected
```

### Checks Performed

- Verified Wazuh Agent service
- Verified manager connectivity
- Verified network communication

### Resolution

Restarted the Wazuh Agent service and confirmed the endpoint became active.

---

## Issue: Delayed Events

### Symptom

Authentication events did not appear immediately.

### Cause

Normal indexing and ingestion delay.

### Resolution

Waited several minutes and refreshed Threat Hunting results.

---

## Issue: Incorrect Search Syntax

### Symptom

Search returned no matching events.

### Resolution

Used:

```text
win.system.eventID:4624
```

for successful logons.

Used:

```text
win.system.eventID:4625
```

for failed logons.

---

## Validation Checklist

- [ ] Agent Active
- [ ] Successful Login Generated
- [ ] Failed Login Generated
- [ ] Event ID 4624 Found
- [ ] Event ID 4625 Found
- [ ] Event Details Reviewed
- [ ] Screenshots Captured

---

## Lessons Learned

- Always verify agent status first.
- Generate fresh events during testing.
- Use Event IDs to quickly locate authentication activity.
- Authentication monitoring is a foundational SOC use case.
