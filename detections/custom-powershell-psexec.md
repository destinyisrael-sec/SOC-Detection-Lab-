# Custom Detection: PowerShell launched PsExec.exe

## Objective

Detect PowerShell spawning **PsExec.exe**, a Microsoft Sysinternals administration utility frequently abused by attackers for remote execution, lateral movement, privilege escalation, and ransomware deployment.

---

## MITRE ATT&CK

- **T1021.002 – Remote Services: SMB/Windows Admin Shares**

---

## Detection Logic

The custom Wazuh rule monitors Microsoft Sysmon Process Creation events (Event ID 1).

### Detection Conditions

- Parent Process = powershell.exe
- Child Process = psexec.exe

The rule identifies suspicious execution where PowerShell launches PsExec, a behavior commonly associated with post-exploitation activity.

---

## Rule Information

- Rule ID: **100109**
- Severity: **13**
- Data Source: Microsoft Sysmon Event ID 1
- Detection Source: Wazuh Custom Rule

---

## Attack Simulation

Executed from PowerShell:

```powershell
powershell -Command "Start-Process PsExec.exe"
```

---

## Detection Result

The custom Wazuh detection successfully identified PowerShell launching **PsExec.exe**.

The alert was generated after Microsoft Sysmon recorded the Process Creation event and Wazuh matched the custom detection rule.

---

## Evidence

- powershell-psexec-alert.png
- powershell-psexec-rule.png

---

## Security Significance

PsExec is commonly associated with:

- Lateral movement
- Remote command execution
- Privilege escalation
- Ransomware deployment
- Post-exploitation activity

Monitoring PowerShell spawning PsExec provides defenders with visibility into suspicious execution behavior and potential attacker movement across Windows environments.

---

## Skills Demonstrated

- Detection Engineering
- Wazuh Custom Rule Development
- Microsoft Sysmon Monitoring
- Windows Endpoint Detection
- Windows Process Analysis
- Threat Hunting
- SIEM Analysis
- MITRE ATT&CK Mapping
- Endpoint Monitoring
