# PowerShell Discovery Activity

## Objective

Generate PowerShell activity that Wazuh detects using Sysmon.

## Commands Used

```powershell
whoami
hostname
net user
```

## Expected Result

Wazuh generates alerts for:

- Discovery activity executed
- PowerShell spawning cmd.exe
- Account discovery
