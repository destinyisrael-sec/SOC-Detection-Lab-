# PowerShell Discovery Detection

## Detection Source

Sysmon Event ID 1

## Wazuh Rules Triggered

- Rule 92031
- Rule 92039
- Rule 92066
- Rule 92205

## Severity

Medium

## Description

PowerShell executed discovery commands including:

- whoami
- hostname
- net user

Wazuh detected the activity and generated alerts for account discovery and suspicious PowerShell execution.
