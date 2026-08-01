# Incident Report 012

## Incident Title

PowerShell launched MSHTA.EXE

---

## Severity

Medium

---

## Executive Summary

A custom Wazuh detection identified **PowerShell launching MSHTA.EXE**.

MSHTA is a legitimate Microsoft utility used to execute HTML Applications (HTA). However, it is widely abused by attackers to execute malicious scripts and payloads while leveraging a trusted Windows binary to evade security controls.

---

## Detection Details

- Rule ID: **100108**
- Severity: **12**
- Detection Source: Wazuh Custom Rule
- Data Source: Microsoft Sysmon Event ID 1
- Parent Process: powershell.exe
- Child Process: mshta.exe

---

## Attack Simulation

The following command was executed from PowerShell:

```powershell
powershell -Command "mshta.exe about:blank"
```

This command safely launched MSHTA to validate the custom detection rule in a controlled lab environment.

---

## MITRE ATT&CK

- **T1218.005 – System Binary Proxy Execution: Mshta**

---

## Detection Timeline

1. PowerShell launched MSHTA.EXE.
2. Microsoft Sysmon recorded a Process Creation event (Event ID 1).
3. Wazuh ingested the Sysmon telemetry.
4. Custom Rule **100108** matched the parent-child process relationship.
5. Wazuh generated a Level 12 security alert for analyst review.

---

## Evidence

- powershell-mshta-alert.png
- powershell-mshta-rule.png

---

## Analyst Findings

The custom Wazuh rule successfully detected **PowerShell spawning MSHTA.EXE**.

MSHTA is commonly abused by threat actors to execute malicious HTA files, remote scripts, and payloads while using a trusted Microsoft binary. Monitoring PowerShell launching MSHTA provides valuable visibility into potential defense evasion and code execution attempts.

The successful detection confirms that the custom rule accurately correlates Sysmon telemetry with suspicious process relationships.

---

## Impact Assessment

No malicious payload was executed during testing.

The activity was intentionally generated within a controlled laboratory environment to validate the effectiveness of the custom Wazuh detection rule.

---

## Recommendations

- Investigate unexpected execution of **MSHTA.EXE** initiated by PowerShell.
- Review command-line arguments for suspicious URLs, scripts, or HTA files.
- Correlate endpoint telemetry with network activity to identify potential malicious payload execution.
- Continue monitoring Windows LOLBins commonly abused for defense evasion and execution.

---

## Skills Demonstrated

- Incident Analysis
- Detection Engineering
- Windows Endpoint Investigation
- Microsoft Sysmon Analysis
- Wazuh SIEM Operations
- Threat Hunting
- MITRE ATT&CK Mapping
