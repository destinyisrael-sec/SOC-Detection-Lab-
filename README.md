# SOC Detection Lab

## Overview

This project demonstrates how to deploy and use Wazuh SIEM to monitor Windows endpoints, detect security events, and investigate alerts.
## Architecture

```text
Windows 11 Endpoint
        │
        │ Wazuh Agent
        ▼
Ubuntu 24.04 (Wazuh Manager)
        │
        ▼
Wazuh Indexer
        │
        ▼
Wazuh Dashboard
```
## Lab Environment

- Ubuntu 24.04 LTS
- Wazuh Manager 4.9.2
- Wazuh Dashboard
- Wazuh Indexer
- Windows 11 Endpoint
- VirtualBox

## Objectives

- Deploy Wazuh SIEM
- Monitor Windows security events
- Detect suspicious activity
- Perform incident investigation
- Document findings
## Skills Demonstrated

- SIEM Deployment
- Wazuh Configuration
- Windows Endpoint Monitoring
- Windows Event Log Analysis
- Threat Hunting
- Alert Triage
- Incident Investigation
- Security Monitoring
- Endpoint Detection
- Log Analysis
## Repository Structure

- screenshots/
- attack-simulations/
- incident-reports/
- detections/
- documentation/

## Detection Scenarios

### Detection 1 – Windows Authentication Failure

- Windows Event ID: **4625**
- Wazuh successfully collected failed logon events.
- Alerts were visible in the Wazuh Dashboard.
- Investigation confirmed multiple failed authentication attempts.

### Detection 2 – Successful Logon

- Windows Event ID: **4624**
- Verified successful Windows authentication events.
- Confirmed endpoint visibility from the Windows agent.

### Detection 3 – Wazuh Agent Health

- Windows endpoint successfully enrolled.
- Agent communication verified.
- Logs successfully forwarded to the manager.
- ## Lessons Learned

- Successfully deployed a complete Wazuh SIEM environment using Ubuntu and Windows 11.
- Learned how to enroll a Windows endpoint with the Wazuh Manager.
- Resolved agent version compatibility issues between the manager and Windows agent.
- Investigated Windows Security Event ID 4625 (failed logon) using the Wazuh Dashboard.
- Learned how to search and filter security events using Wazuh queries.
- Practiced troubleshooting Wazuh services, agent enrollment, and configuration issues.
- Improved documentation and GitHub project organization for a professional cybersecurity portfolio.
