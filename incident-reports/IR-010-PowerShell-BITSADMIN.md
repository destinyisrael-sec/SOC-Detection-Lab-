# Incident Report 010

## Incident Title

PowerShell launched BITSADMIN.EXE

---

## Severity

Medium

---

## Executive Summary

A custom Wazuh detection identified **PowerShell launching BITSADMIN.EXE**.

BITSADMIN is a legitimate Windows administration utility designed to manage Background Intelligent Transfer Service (BITS) jobs. However, threat actors have historically abused it to download malware, transfer payloads, and evade traditional security monitoring by blending malicious traffic with legitimate Windows background transfers.

---

## Detection Details

- Rule ID: 100106
- Severity: 12
- Detection Source: Wazuh Custom Rule
- Data Source: Microsoft Sysmon Event ID 1
- Parent Process: powershell.exe
- Child Process: bitsadmin.exe

---

## Attack Simulation

The following command was executed from PowerShell to simulate the activity:

```powershell
powershell -Command "bitsadmin /?"
```

Alternative execution used during testing:

```powershell
powershell -Command "Start-Process bitsadmin.exe -ArgumentList '/?'"
```

---

## MITRE ATT&CK

- **T1105 – Ingress Tool Transfer**

---

## Detection Timeline

1. PowerShell executed BITSADMIN.EXE.
2. Microsoft Sysmon recorded a Process Creation event (Event ID 1).
3. Wazuh ingested the Sysmon event.
4. Custom Rule **100106** matched the parent-child process relationship.
5. Wazuh generated a Level 12 alert for analyst review.

---

## Evidence

- powershell-bitsadmin-alert.png
- powershell-bitsadmin-rule.png

---

## Analyst Findings

The custom Wazuh rule successfully detected PowerShell spawning **BITSADMIN.EXE**.

This behavior is considered suspicious because attackers frequently abuse BITSADMIN as a Living-Off-the-Land Binary (LOLBin) to download or transfer malicious payloads while attempting to blend in with legitimate Windows activity.

The successful detection confirms that the custom rule correctly identifies suspicious parent-child process relationships using Sysmon telemetry.

---

## Impact Assessment

No malicious payload was transferred during testing. The activity was intentionally generated in a controlled laboratory environment to validate the effectiveness of the custom Wazuh detection rule.

---

## Recommendations

- Investigate any unexpected execution of **BITSADMIN.EXE** launched by PowerShell.
- Correlate with network activity to identify potential unauthorized file transfers.
- Review the command line used to determine whether BITSADMIN was executed for administrative purposes or malicious intent.
- Continue monitoring for LOLBin abuse across Windows endpoints.
