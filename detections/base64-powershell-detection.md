# Base64 Encoded PowerShell Detection

## Detection Overview

This detection identifies PowerShell processes that execute Base64 encoded commands.

Attackers commonly use Base64 encoded PowerShell to hide malicious scripts and bypass simple detections.

---

## Detection Rule

**Rule ID:** 92057

**Severity:** 12

**Description:**

PowerShell.exe spawned a PowerShell process which executed a Base64 encoded command.

---

## MITRE ATT&CK

Technique: T1059.001

PowerShell

---

## Wazuh Detection

The event was successfully detected by Wazuh.

Alert generated:

- Rule ID: 92057
- Severity: 12

---

## Evidence

See screenshots:

- Threat Hunting alert list
- Rule details

---

## Skills Demonstrated

- Threat Hunting
- Endpoint Monitoring
- Detection Engineering
- SIEM Analysis
- PowerShell Detection
- Windows Event Investigation
