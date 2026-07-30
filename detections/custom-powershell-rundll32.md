# Custom Detection: PowerShell launched RUNDLL32.EXE

## Objective

Detect PowerShell spawning **RUNDLL32.EXE**, a Windows Living-Off-the-Land Binary (LOLBin) commonly abused by attackers to execute malicious DLLs, bypass application controls, and evade traditional endpoint security solutions.

---

## MITRE ATT&CK

- **T1218.011 – System Binary Proxy Execution: Rundll32**

---

## Detection Logic

The custom Wazuh rule monitors Microsoft Sysmon Process Creation events (Event ID 1).

### Detection Conditions

- Parent Process = powershell.exe
- Child Process = rundll32.exe

The rule identifies suspicious execution of **RUNDLL32.EXE** when launched directly from PowerShell, a behavior frequently associated with post-exploitation techniques and defense evasion.

---

## Rule Information

- Rule ID: **100107**
- Severity: **12**
- Data Source: Microsoft Sysmon Event ID 1
- Detection Source: Wazuh Custom Rule

---

## Attack Simulation

Executed from PowerShell:

```powershell
powershell -Command "rundll32.exe shell32.dll,Control_RunDLL"
```

---

## Detection Result

The custom Wazuh detection successfully identified PowerShell launching **RUNDLL32.EXE**.

The alert was generated immediately after Sysmon recorded the Process Creation event.

---

## Evidence

- powershell-rundll32-alert.png
- powershell-rundll32-rule.png

---

## Security Significance

RUNDLL32.EXE is a legitimate Windows binary used to execute DLL functions.

Threat actors frequently abuse it to:

- Execute malicious DLL payloads
- Evade application allowlisting
- Execute malware using trusted Windows binaries
- Blend malicious activity with legitimate operating system processes

Monitoring parent-child process relationships involving PowerShell and RUNDLL32 significantly improves visibility into suspicious endpoint activity.

---

## Skills Demonstrated

- Detection Engineering
- Wazuh Custom Rule Development
- Microsoft Sysmon Monitoring
- Windows Endpoint Detection
- LOLBin Detection
- Threat Detection
- SIEM Analysis
- MITRE ATT&CK Mapping
- Endpoint Monitoring
