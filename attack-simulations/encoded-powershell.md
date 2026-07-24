# Encoded PowerShell Execution

## Objective

Simulate a common attacker technique using a Base64-encoded PowerShell command.

## Command Executed

```powershell
powershell.exe -EncodedCommand VwByAGkAdABlAC0ATwB1AHQAcAB1AHQAIAAiAFMAeQBzAG0AbwBuACAAVABlAHMAdAAiAA==
```

## Expected Detection

- Encoded PowerShell execution
- Suspicious PowerShell behavior
- Executable file creation

## MITRE ATT&CK

- T1059.001 – PowerShell
- T1027 – Obfuscated Files or Information
