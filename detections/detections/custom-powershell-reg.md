## Findings

A custom Wazuh detection rule was developed to identify PowerShell launching REG.EXE.

Although Microsoft Sysmon successfully generated the process creation event and Wazuh successfully ingested the event, the custom detection rule did not trigger after multiple iterations.

The investigation included:

- Verifying Sysmon Event ID 1 logging.
- Validating local_rules.xml syntax.
- Restarting the Wazuh Manager.
- Testing the rule with reg.exe execution.
- Reviewing ParentImage and Image fields.
- Adjusting regex matching.

The investigation demonstrated practical experience troubleshooting SIEM detection logic and validating endpoint telemetry.

Result:
Telemetry successfully verified.
Custom detection requires additional tuning.
