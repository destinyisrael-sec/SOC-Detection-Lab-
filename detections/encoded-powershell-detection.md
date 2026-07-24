# Encoded PowerShell Detection

## Detection Source

Sysmon Event ID 1

## Wazuh Rules Triggered

- Rule 92057
- Rule 92213

## Severity

12 (High)

15 (Critical)

## Description

A Base64-encoded PowerShell command was executed. Wazuh detected the encoded command execution and the creation of an executable file in a suspicious location.

## MITRE ATT&CK

- T1059.001
- T1027
