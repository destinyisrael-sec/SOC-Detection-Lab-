# Custom Detection: PowerShell launched BITSADMIN.EXE

## Objective

Detect PowerShell spawning **BITSADMIN.EXE**, a Windows Living-Off-the-Land Binary (LOLBin) historically abused by attackers to download, upload, or transfer malicious payloads while blending in with legitimate Background Intelligent Transfer Service (BITS) activity.

---

## MITRE ATT&CK

- T1105 – Ingress Tool Transfer

---

## Detection Logic

The custom Wazuh rule monitors Sysmon Process Creation (Event ID 1).

Detection conditions:

- Parent Process = powershell.exe
- Child Process = bitsadmin.exe

The detection identifies suspicious use of BITSADMIN when launched from PowerShell, a behavior commonly associated with post-exploitation activity.

---

## Rule Information

- Rule ID: 100106
- Severity: 12
- Data Source: Microsoft Sysmon Event ID 1

---

## Attack Simulation

Executed from PowerShell:

```powershell
powershell -Command "bitsadmin /?"
```

Alternative execution:

```powershell
powershell -Command "Start-Process bitsadmin.exe -ArgumentList '/?'"
```

---

## Detection Result

The custom Wazuh rule successfully detected PowerShell launching BITSADMIN.EXE.

The alert was generated immediately after Sysmon recorded the Process Creation event.

---

## Evidence

- powershell-bitsadmin-alert.png
- powershell-bitsadmin-rule.png

---

## Security Significance

BITSADMIN has historically been abused by malware and advanced persistent threats (APTs) to transfer malicious payloads while attempting to evade traditional security controls.

Detecting PowerShell launching BITSADMIN provides defenders with visibility into potentially malicious file transfer activity.

---

## Skills Demonstrated

- Detection Engineering
- Wazuh Custom Rule Development
- Endpoint Detection
- Sysmon Monitoring
- LOLBin Detection
- MITRE ATT&CK Mapping
- Threat Detection
- SIEM Analysis
