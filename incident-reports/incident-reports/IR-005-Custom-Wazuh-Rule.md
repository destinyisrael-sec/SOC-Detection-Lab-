# Incident Report 005

## Incident

Custom Wazuh Rule Triggered

---

## Alert

Rule ID:
100100

Severity:
10

Description:
Custom Detection: PowerShell launched Notepad

---

## Investigation

Observed that PowerShell launched Notepad.

The behavior matched the custom detection logic configured inside local_rules.xml.

The alert confirmed that the custom rule works correctly.

---

## MITRE ATT&CK

T1059.001
PowerShell

---

## Outcome

Rule successfully validated.

No false positives observed.

---

## Skills Demonstrated

Detection Engineering

SIEM Rule Development

Threat Detection

PowerShell Monitoring
