# Custom Detection: PowerShell Launching CMD

## Objective

Detect when PowerShell launches Command Prompt.

## Rule ID

100101

## Severity

12

## Detection Logic

Parent Process:
powershell.exe

Child Process:
cmd.exe

## MITRE ATT&CK

T1059
Command and Scripting Interpreter

## Evidence

- Screenshot of Wazuh alert
- Screenshot of custom rule

## Skills Demonstrated

Detection Engineering
Wazuh Rule Development
PowerShell Monitoring
Process Creation Analysis
MITRE ATT&CK Mapping
