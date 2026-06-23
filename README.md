# Wazuh-Lab-02-Windows-Authentication-Monitoring

## Overview

This lab demonstrates how to monitor Windows authentication activity using Wazuh.

A Windows endpoint enrolled in Wazuh was used to generate successful and failed logon events. These events were then investigated through the Wazuh Dashboard to understand how authentication activity appears from a SOC analyst's perspective.

---

## Lab Goals

- Generate successful login events
- Generate failed login events
- Search authentication events in Wazuh
- Investigate Event ID 4624
- Investigate Event ID 4625
- Practice basic authentication monitoring

---

## Environment

| Component | Details |
|------------|------------|
| Wazuh Manager | Rocky Linux 9 |
| Wazuh Dashboard | Wazuh 4.x |
| Endpoint | Windows 11 |
| Agent | Wazuh Agent |
| Network | NAT (VMnet8) |

---

## Events Investigated

| Event ID | Description |
|------------|------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

---

## Lab Steps

### 1. Verify Agent Status

Navigate to:

```text
Wazuh → Agents
```

Verify the Windows endpoint is active.

---

### 2. Generate Successful Login Activity

Lock the workstation:

```text
Win + L
```

Log back in using valid credentials.

---

### 3. Generate Failed Login Activity

Lock the workstation again.

Attempt to log in with an incorrect password multiple times.

---

### 4. Search Successful Logins

Navigate to:

```text
Threat Hunting
```

Search:

```text
win.system.eventID:4624
```

---

### 5. Search Failed Logins

Search:

```text
win.system.eventID:4625
```

---

### 6. Review Event Details

Review:

- User Account
- Timestamp
- Logon Type
- Computer Name
- Failure Reason

---

## Results

- Successfully generated Event ID 4624
- Successfully generated Event ID 4625
- Authentication events were collected by Wazuh
- Events were searchable in Threat Hunting
- User activity could be reconstructed from collected logs

---


## Skills Practiced

- Wazuh SIEM
- Windows Authentication Monitoring
- Security Event Analysis
- Threat Hunting
- SOC Investigation Workflow
