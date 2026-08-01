# Threat Hunt 004 - Process Creation & LOLBin Investigation

## Objective

Investigate suspicious Windows process creation events and identify Living-off-the-Land Binary (LOLBin) abuse.

---

## Hunt Hypothesis

Attackers frequently abuse legitimate Windows binaries to execute malicious actions while avoiding detection.

Monitoring parent-child process relationships helps identify suspicious execution chains.

---

## Environment

SIEM
- Wazuh

Endpoint
- Windows 11
- Sysmon

---

## Hunt Queries

Rule IDs

92004
92057
100100

Keywords

powershell

cmd

process

---

## Investigation

Observed Activity

✔ PowerShell spawned child processes

✔ Command shell launched

✔ Encoded PowerShell executed

✔ Custom detection triggered

---

## Parent / Child Process Chain

PowerShell.exe

↓

cmd.exe

↓

Additional child processes

---

## MITRE ATT&CK

T1059

Command and Scripting Interpreter

T1218

Signed Binary Proxy Execution

---

## Findings

The investigation identified multiple suspicious parent-child relationships involving PowerShell.

These behaviors closely resemble attacker tradecraft used during post-exploitation.

---

## Skills Demonstrated

- Threat Hunting
- Process Tree Analysis
- LOLBin Investigation
- Detection Engineering
- Endpoint Monitoring
- MITRE ATT&CK Mapping

---

## Evidence

- Process Creation Alerts

- PowerShell Alerts

- Custom Rule Alert

---

## Outcome

Successfully reconstructed suspicious process execution and validated endpoint telemetry using Sysmon and Wazuh.
