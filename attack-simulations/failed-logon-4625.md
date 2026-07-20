# Failed Logon Simulation (Windows Event ID 4625)

## Objective

Simulate failed Windows login attempts and verify that Wazuh detects and reports the activity.

## Lab Environment

- Ubuntu 24.04 LTS
- Wazuh Manager 4.9.2
- Wazuh Dashboard
- Windows 11 Endpoint
- Wazuh Agent 4.9.2

## Steps Performed

1. Logged into the Windows 11 endpoint.
2. Entered an incorrect password multiple times.
3. Allowed Windows to generate failed authentication events.
4. Waited for the Wazuh agent to forward the logs.
5. Opened the Wazuh Dashboard.
6. Searched for Windows Event ID 4625.

## Expected Result

The failed logon attempts should generate Windows Security Event ID 4625 and appear as alerts in the Wazuh Dashboard.

## Actual Result

The Wazuh Dashboard successfully detected the failed authentication attempts.

## Evidence

See the screenshots in the `screenshots/` folder.

## MITRE ATT&CK

- T1110 – Brute Force

## Conclusion

The Windows endpoint successfully generated failed authentication events, and the Wazuh SIEM detected and indexed the activity correctly.
