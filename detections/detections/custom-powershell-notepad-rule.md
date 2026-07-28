# Custom Detection Rule – PowerShell Launching Notepad

## Objective

Create a custom Wazuh detection rule capable of detecting PowerShell launching Notepad.

---

## Detection Logic

Rule ID: 100100

Parent Process:
powershell.exe

Child Process:
notepad.exe

Severity:
10

---

## MITRE ATT&CK

T1059.001
PowerShell

---

## Validation

The rule successfully generated an alert after executing:

powershell.exe
↓

notepad.exe

Alert generated:

Rule ID:
100100

Level:
10

Description:
Custom Detection: PowerShell launched Notepad

---

## Skills Demonstrated

Detection Engineering

Custom SIEM Rule Development

Wazuh Rule Creation

PowerShell Monitoring

Process Creation Analysis

MITRE ATT&CK Mapping
