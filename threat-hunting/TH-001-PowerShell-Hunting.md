# Threat Hunt 001 - Suspicious PowerShell Activity

## Objective

Identify suspicious PowerShell execution that may indicate malicious activity on monitored Windows endpoints.

---

## Hunt Hypothesis

Attackers frequently abuse PowerShell to execute malicious commands, perform reconnaissance, download malware, or execute Base64 encoded payloads.

This hunt was designed to identify:

- Encoded PowerShell commands
- PowerShell spawned processes
- Suspicious child processes
- LOLBin abuse

---

## Environment

SIEM:
- Wazuh 4.x

Endpoint:
- Windows 11
- Sysmon Installed

MITRE ATT&CK

- T1059.001 — PowerShell
- T1082 — System Information Discovery
- T1087 — Account Discovery

---

## Hunt Query

Threat Hunting Search

Rule IDs:

92057
92031
92039
92004
100100

---

## Investigation

Observed Events

✔ Base64 Encoded PowerShell detected

✔ Account Discovery executed

✔ Process creation observed

✔ PowerShell launched additional processes

✔ Custom Wazuh detection triggered

---

## Timeline

1. PowerShell launched.

2. Encoded command executed.

3. Account discovery performed.

4. Child process created.

5. Custom Wazuh rule triggered.

---

## Findings

The activity matched common attacker behavior for:

- Initial Execution
- Discovery
- Living-off-the-Land (LOLBins)

The custom detection rule successfully identified suspicious PowerShell behavior in addition to Wazuh's built-in detections.

---

## Skills Demonstrated

- Threat Hunting
- SIEM Investigation
- Detection Validation
- Endpoint Monitoring
- MITRE ATT&CK Mapping
- Detection Engineering

---

## Screenshots

- Threat Hunting dashboard
- Rule 92057
- Rule 100100
- Event Details

---

## Outcome

Successfully validated both built-in and custom Wazuh detections for suspicious PowerShell execution.
