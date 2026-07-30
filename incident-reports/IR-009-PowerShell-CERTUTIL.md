# Incident Report 009

## Incident Title

PowerShell launched CERTUTIL.EXE

---

## Severity

Medium

---

## Summary

A custom Wazuh detection identified PowerShell launching the Windows LOLBin **CERTUTIL.EXE**.

Although Certutil is a legitimate Windows utility, attackers frequently abuse it to download payloads, decode Base64 data, and transfer malicious files.

---

## Detection Details

- Rule ID: 100105
- Severity: 12
- Detection Source: Wazuh Custom Rule
- Data Source: Sysmon Event ID 1

---

## Attack Simulation

Executed:

```powershell
powershell -Command "certutil -hashfile C:\Windows\System32\notepad.exe SHA256"
```

---

## MITRE ATT&CK

- T1105 – Ingress Tool Transfer

---

## Evidence

- powershell-certutil-alert.png
- powershell-certutil-rule.png

---

## Analyst Findings

The custom Wazuh rule successfully detected PowerShell spawning CERTUTIL.EXE.

This behavior is commonly associated with attacker tradecraft because Certutil can be abused to download files, decode payloads, and evade security controls.

---

## Recommendation

Investigate any unexpected execution of CERTUTIL.EXE launched from PowerShell, especially on production endpoints. Verify whether the activity is administrative or potentially malicious.
