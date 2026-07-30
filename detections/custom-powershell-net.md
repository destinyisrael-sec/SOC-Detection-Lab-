# Custom Detection: PowerShell launched NET.EXE

## Objective

Detect PowerShell spawning the Windows LOLBin **NET.EXE**, commonly used for account enumeration and system discovery.

---

## MITRE ATT&CK

- T1087 – Account Discovery
- T1059.001 – PowerShell

---

## Detection Logic

The custom Wazuh rule monitors Sysmon Process Creation (Event ID 1).

Detection conditions:

- Parent Process = powershell.exe
- Child Process = net.exe

---

## Rule Information

- Rule ID: 100104
- Severity: 12

---

## Attack Simulation

Executed from PowerShell:

```powershell
powershell -Command "net user"
```

---

## Detection Result

The activity successfully triggered the custom Wazuh detection.

Evidence:

- powershell-net-alert.png
- powershell-net-rule.png

---

## Skills Demonstrated

- Detection Engineering
- Wazuh Rule Development
- Sysmon Monitoring
- PowerShell Detection
- Windows LOLBins
- MITRE ATT&CK Mapping
