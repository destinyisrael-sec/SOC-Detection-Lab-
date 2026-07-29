# Custom Wazuh Detection Rules

This folder contains custom Wazuh detection rules developed as part of my SOC Detection Engineering Lab.

## Objectives

- Develop custom detection logic
- Validate detection rules against simulated attacks
- Map detections to the MITRE ATT&CK framework
- Improve detection engineering skills

## Custom Rules

| Rule ID | Description | MITRE ATT&CK |
|---------|-------------|--------------|
|100100|PowerShell launched Notepad|T1059.001|
|100101|PowerShell launched CMD|T1059.001|
|100102|PowerShell launched WScript|T1059.001|
|100103|PowerShell launched REG.EXE|T1112|
|100104|PowerShell launched NET.EXE|T1087|
|100105|PowerShell launched CertUtil|T1105|
|100106|PowerShell launched BitsAdmin|T1197|
|100107|PowerShell launched Rundll32|T1218.011|
|100108|PowerShell launched MSHTA|T1218.005|
|100109|PowerShell launched PsExec|T1021.002|

Each rule has been tested inside my Wazuh detection lab using Windows 11, Sysmon, and Wazuh SIEM.
