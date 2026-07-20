# Successful Logon Simulation (Windows Event ID 4624)

## Objective

Verify that Wazuh detects successful Windows logon events.

## Lab Environment

- Ubuntu 24.04 LTS
- Wazuh Manager 4.9.2
- Wazuh Dashboard
- Windows 11 Endpoint
- Wazuh Agent 4.9.2

## Steps Performed

1. Logged into the Windows endpoint successfully.
2. Waited for the Wazuh agent to forward logs.
3. Opened the Wazuh Dashboard.
4. Searched for Windows Event ID 4624.

## Expected Result

Successful logon events should appear in Wazuh.

## Actual Result

Wazuh successfully detected the successful authentication event.

## Evidence

See screenshots folder.

## MITRE ATT&CK

- T1078 – Valid Accounts

## Conclusion

The endpoint successfully generated Windows Event ID 4624 and Wazuh detected it correctly.
