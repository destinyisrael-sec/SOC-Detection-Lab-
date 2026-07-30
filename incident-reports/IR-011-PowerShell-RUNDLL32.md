# Incident Report 011

## Incident Title

PowerShell launched RUNDLL32.EXE

---

## Severity

Medium

---

## Executive Summary

A custom Wazuh detection identified **PowerShell launching RUNDLL32.EXE**.

Although **RUNDLL32.EXE** is a legitimate Windows utility designed to execute DLL functions, it is widely abused by attackers to execute malicious code while leveraging trusted Microsoft binaries to evade security controls.

---

## Detection Details

- Rule ID: **100107**
- Severity: **12**
- Detection Source: Wazuh Custom Rule
- Data Source: Microsoft Sysmon Event ID 1
- Parent Process: powershell.exe
- Child Process: rundll32.exe

---

## Attack Simulation

The following command was executed from PowerShell:

```powershell
powershell -Command "rundll32.exe shell32.dll,Control_RunDLL"
```

This command safely launches the Windows Control Panel using **RUNDLL32.EXE** for detection validation purposes.

---

## MITRE ATT&CK

- **T1218.011 – System Binary Proxy Execution: Rundll32**

---

## Detection Timeline

1. PowerShell executed RUNDLL32.EXE.
2. Microsoft Sysmon generated a Process Creation event (Event ID 1).
3. Wazuh ingested the Sysmon telemetry.
4. Custom Rule **100107** matched the parent-child process relationship.
5. Wazuh generated a Level 12 security alert for analyst review.

---

## Evidence

- powershell-rundll32-alert.png
- powershell-rundll32-rule.png

---

## Analyst Findings

The custom Wazuh rule successfully detected **PowerShell spawning RUNDLL32.EXE**.

RUNDLL32 is frequently used by threat actors to execute malicious DLLs while masquerading as legitimate Windows activity. Monitoring this behavior enables defenders to identify potential defense evasion and code execution attempts.

The detection confirms that the custom rule correctly correlates Sysmon Process Creation events with suspicious parent-child process relationships.

---

## Impact Assessment

No malicious code was executed during testing.

The activity was intentionally performed within a controlled laboratory environment to validate the effectiveness of the custom Wazuh detection rule.

---

## Recommendations

- Investigate unexpected executions of **RUNDLL32.EXE** initiated by PowerShell.
- Review the command line arguments supplied to RUNDLL32.EXE.
- Correlate endpoint events with network activity to identify potential malware execution.
- Continue monitoring Windows LOLBins commonly abused during post-exploitation.

---

## Skills Demonstrated

- Incident Analysis
- Detection Engineering
- Endpoint Detection
- Windows Process Investigation
- Microsoft Sysmon Analysis
- Wazuh SIEM Operations
- Threat Hunting
- MITRE ATT&CK Mapping
