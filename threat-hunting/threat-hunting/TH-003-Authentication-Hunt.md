# Threat Hunt 003 - Windows Authentication Investigation

## Objective

Investigate Windows authentication events to identify failed logon attempts, successful authentications, and potential brute force activity.

---

## Hunt Hypothesis

Repeated authentication failures followed by a successful login may indicate password spraying, brute force attacks, or unauthorized access attempts.

---

## Environment

SIEM
- Wazuh

Endpoint
- Windows 11
- Sysmon

---

## Hunt Queries

Rule IDs

60122
60106

Windows Events

4625
4624

---

## Investigation

Observed Events

✔ Multiple failed authentication attempts detected

✔ Successful authentication recorded

✔ Authentication timeline successfully reconstructed

---

## Timeline

1. Failed logon attempts generated.

2. Wazuh created authentication alerts.

3. Successful authentication occurred.

4. Events correlated during threat hunting.

---

## MITRE ATT&CK

T1110

Brute Force

Credential Access

---

## Findings

Authentication monitoring successfully detected both failed and successful Windows logon events.

The event sequence demonstrates how Wazuh can identify suspicious authentication behavior and assist analysts during credential abuse investigations.

---

## Skills Demonstrated

- Threat Hunting
- Authentication Analysis
- Windows Event Logs
- Endpoint Monitoring
- SIEM Investigation
- MITRE ATT&CK Mapping

---

## Evidence

- Failed Authentication alerts
- Successful Logon alerts
- Threat Hunting dashboard

---

## Outcome

Successfully validated authentication monitoring and demonstrated reconstruction of Windows logon activity using Wazuh.
