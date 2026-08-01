# Incident Report 013

## Incident Title

PowerShell launched PsExec.exe

---

## Severity

High

---

## Executive Summary

A custom Wazuh detection identified **PowerShell launching PsExec.exe**.

PsExec is a legitimate Microsoft Sysinternals administration utility used for remote process execution. Threat actors frequently abuse it during lateral movement, ransomware deployment, and post-compromise activities.

---

## Detection Details

- Rule ID: **100109**
- Severity: **13**
- Detection Source: Wazuh Custom Rule
- Data Source: Microsoft Sysmon Event ID 1
- Parent Process: powershell.exe
- Child Process: psexec.exe

---

## Attack Simulation

Executed from PowerShell:

```powershell
powershell -Command "Start-Process PsExec.exe"
```

The command was executed within a controlled SOC laboratory environment to validate the custom Wazuh detection rule.

---

## MITRE ATT&CK

- **T1021.002 – Remote Services: SMB/Windows Admin Shares**

---

## Detection Timeline

1. PowerShell launched PsExec.exe.
2. Microsoft Sysmon generated a Process Creation event (Event ID 1).
3. Wazuh ingested the Sysmon telemetry.
4. Custom Rule **100109** matched the parent-child process relationship.
5. Wazuh generated a Level 13 alert for investigation.

---

## Evidence

- powershell-psexec-alert.png
- powershell-psexec-rule.png

---

## Analyst Findings

The custom Wazuh rule successfully detected PowerShell spawning PsExec.exe.

The detection demonstrates the ability to identify suspicious parent-child process relationships commonly observed during attacker lateral movement and remote administration activity.

Although this event was intentionally generated in a controlled laboratory environment, similar behavior in production environments should be investigated immediately because PsExec is frequently abused during real-world attacks.

---

## Impact Assessment

No unauthorized remote execution occurred during testing.

The activity was intentionally generated within a controlled laboratory environment to validate the effectiveness of the custom Wazuh detection rule.

---

## Recommendations

- Investigate unexpected PsExec execution on Windows endpoints.
- Review command-line arguments associated with PsExec execution.
- Correlate endpoint activity with authentication and network events.
- Monitor for additional indicators of lateral movement.
- Restrict unauthorized use of administrative utilities.

---

## Skills Demonstrated

- Incident Response
- Detection Engineering
- Wazuh SIEM Operations
- Microsoft Sysmon Analysis
- Windows Endpoint Investigation
- Threat Hunting
- MITRE ATT&CK Mapping
