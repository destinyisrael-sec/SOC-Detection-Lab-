# Custom Detection: PowerShell launched CERTUTIL.EXE

## Objective

Detect PowerShell spawning the Windows LOLBin **CERTUTIL.EXE**, a binary commonly abused by attackers to download files, decode Base64 payloads, and transfer malicious content.

---

## MITRE ATT&CK

- T1105 – Ingress Tool Transfer

---

## Detection Logic

The custom Wazuh rule monitors Sysmon Process Creation (Event ID 1).

Detection conditions:

- Parent Process = powershell.exe
- Child Process = certutil.exe

---

## Rule Information

- Rule ID: 100105
- Severity: 12

---

## Attack Simulation

Executed from PowerShell:

```powershell
powershell -Command "certutil -hashfile C:\Windows\System32\notepad.exe SHA256"
```

---

## Detection Result

The activity successfully triggered the custom Wazuh detection.

### Evidence

- powershell-certutil-alert.png
- powershell-certutil-rule.png

---

## Skills Demonstrated

- Detection Engineering
- Wazuh Rule Development
- Sysmon Monitoring
- PowerShell Detection
- Windows LOLBins
- MITRE ATT&CK Mapping
- Endpoint Monitoring
