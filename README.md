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
- SIEM Deployment
- Windows Log Analysis
- Threat Detection
- Incident Investigation
- Endpoint Monitoring
- Linux Administration
- Windows Event Log Analysis
- GitHub Documentation
  
- ## Tools Used

- Wazuh SIEM
- Windows 11
- Ubuntu 24.04
- VirtualBox
- Git
- GitHub
  
## Repository Structure

- screenshots/
- attack-simulations/
- incident-reports/
- detections/
- documentation/

## Detection Scenarios

- Windows failed authentication
- Windows successful authentication
- PowerShell spawning CMD
- Account Discovery (net.exe)
- PowerShell LOLBin detection
- Discovery activity detection
- Suspicious executable creation
  
- ✔ Windows Authentication Monitoring

✔ Sysmon Process Monitoring

✔ PowerShell Discovery Detection

✔ Account Enumeration Detection

✔ Process Creation Monitoring

- ## Lessons Learned
  
- Successfully deployed a complete Wazuh SIEM environment using Ubuntu and Windows 11.
- Learned how to enroll a Windows endpoint with the Wazuh Manager.
- Resolved agent version compatibility issues between the manager and Windows agent.
- Investigated Windows Security Event ID 4625 (failed logon) using the Wazuh Dashboard.
- Learned how to search and filter security events using Wazuh queries.
- Practiced troubleshooting Wazuh services, agent enrollment, and configuration issues.
- Improved documentation and GitHub project organization for a professional cybersecurity portfolio.
