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

## Repository Structure

- screenshots/
- attack-simulations/
- incident-reports/
- detections/
- documentation/

## Status

✅ Wazuh SIEM successfully deployed.

✅ Windows agent connected.

⏳ Detection scenarios in progress.
