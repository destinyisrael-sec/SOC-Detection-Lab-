# Incident Report 008

## Title

PowerShell launched NET.EXE

---

## Severity

Medium

---

## Summary

A PowerShell process launched the Windows utility NET.EXE.

This behavior is commonly associated with account discovery and reconnaissance activities.

---

## Timeline

PowerShell executed:

```powershell
powershell -Command "net user"
```

↓

NET.EXE launched

↓

Sysmon generated Process Creation Event ID 1

↓

Custom Wazuh Rule 100104 triggered

---

## MITRE ATT&CK

- T1087 – Account Discovery
- T1059.001 – PowerShell

---

## Evidence

- powershell-net-alert.png
- powershell-net-rule.png

---

## Analyst Notes

The custom detection successfully identified PowerShell spawning NET.EXE.

This technique is frequently observed during attacker reconnaissance.

---

## Recommendation

Investigate any unexpected execution of NET.EXE launched by PowerShell, especially on production systems.
