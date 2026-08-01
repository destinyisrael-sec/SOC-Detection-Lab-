# Custom Detection: PowerShell launched MSHTA.EXE

## Objective

Detect PowerShell spawning **MSHTA.EXE**, a Windows Living-Off-the-Land Binary (LOLBin) frequently abused by attackers to execute malicious HTA applications, launch remote payloads, and bypass traditional application control mechanisms.

---

## MITRE ATT&CK

- **T1218.005 – System Binary Proxy Execution: Mshta**

---

## Detection Logic

The custom Wazuh rule monitors Microsoft Sysmon Process Creation events (Event ID 1).

### Detection Conditions

- Parent Process = powershell.exe
- Child Process = mshta.exe

The rule identifies suspicious execution of **MSHTA.EXE** when launched directly from PowerShell, a behavior commonly associated with defense evasion and malicious code execution.

---

## Rule Information

- Rule ID: **100108**
- Severity: **12**
- Data Source: Microsoft Sysmon Event ID 1
- Detection Source: Wazuh Custom Rule

---

## Attack Simulation

Executed from PowerShell:

```powershell
powershell -Command "mshta.exe about:blank"
```

---

## Detection Result

The custom Wazuh rule successfully detected PowerShell launching **MSHTA.EXE**.

The alert was generated immediately after Microsoft Sysmon recorded the Process Creation event.

---

## Evidence

- powershell-mshta-alert.png
- powershell-mshta-rule.png

---

## Security Significance

MSHTA.EXE is a trusted Windows binary designed to execute HTML Applications (HTA).

Threat actors frequently abuse MSHTA to:

- Execute malicious HTA files
- Launch remote scripts
- Bypass application control
- Execute payloads while blending in with legitimate Windows processes

Detecting PowerShell spawning MSHTA provides defenders with visibility into suspicious post-exploitation techniques.

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
