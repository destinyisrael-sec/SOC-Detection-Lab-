# Incident Report 006 – PowerShell Launching CMD

## Date

July 30, 2026

## Alert

Rule ID: 100101

Severity: 12

## Summary

A custom Wazuh detection rule identified PowerShell spawning Command Prompt (cmd.exe).

This behavior is commonly associated with attackers attempting to execute additional commands after gaining access to a system.

## Evidence

- Screenshot of Threat Hunting alert
- Screenshot of custom rule
- Rule ID 100101

## MITRE ATT&CK

T1059.001

PowerShell

## Detection Logic

Parent Process

powershell.exe

Child Process

cmd.exe

## Analyst Notes

The custom detection rule functioned successfully.

PowerShell was used to launch cmd.exe during testing, and Wazuh generated the expected alert.

## Skills Demonstrated

- Detection Engineering
- Wazuh SIEM
- Sysmon
- PowerShell Monitoring
- Endpoint Detection
- Incident Documentation
