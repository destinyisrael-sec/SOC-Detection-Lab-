# Custom Detection: PowerShell launched PsExec

## Objective

Detect PowerShell spawning **PsExec.exe**, a Windows administration utility commonly abused by attackers for remote command execution, lateral movement, and post-exploitation activities.

PsExec is a legitimate Sysinternals tool used by administrators to remotely execute processes. However, threat actors frequently abuse it during intrusions because it allows execution through trusted Windows mechanisms.

---

## MITRE ATT&CK

- **T1021.002 – Remote Services: SMB/Windows Admin Shares**

---

## Detection Logic

The custom Wazuh rule monitors Microsoft Sysmon Process Creation events (Event ID 1).

### Detection Conditions

- Parent Process = powershell.exe
- Child Process = psexec.exe

The rule detects suspicious execution chains where PowerShell launches PsExec, which may indicate lateral movement or unauthorized remote execution activity.

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
