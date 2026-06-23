# Investigation Notes

## Objective

Validate that Windows authentication events are successfully collected and searchable within Wazuh.

---

## Successful Login Investigation

### Search Query

```text
win.system.eventID:4624
```

### Expected Result

Successful authentication event.

### Information Reviewed

- Username
- Timestamp
- Logon Type
- Endpoint Name

### Outcome

Successful login activity was detected and visible in Wazuh.

---

## Failed Login Investigation

### Search Query

```text
win.system.eventID:4625
```

### Expected Result

Failed authentication event.

### Information Reviewed

- Account Name
- Failure Reason
- Timestamp
- Endpoint Name

### Outcome

Failed login attempts were detected and visible in Wazuh.

---

## Event Correlation

Compared:

```text
Event ID 4624
Event ID 4625
```

Questions Reviewed:

- Which account attempted login?
- Were failed logins observed?
- Was a successful login observed afterward?
- Does activity appear suspicious?

---

## Findings

- Wazuh successfully collected Windows authentication events.
- Both successful and failed logins were visible.
- Events could be filtered using Event IDs.
- Authentication activity was easily traceable.

---

## Conclusion

The Windows endpoint successfully forwarded authentication telemetry to Wazuh, providing visibility into user login activity and failed authentication attempts.
