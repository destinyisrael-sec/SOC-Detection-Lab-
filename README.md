# SOC Detection Engineering Lab

> A hands-on Security Operations Center (SOC) portfolio focused on Detection Engineering, Threat Hunting, Incident Response, and Endpoint Monitoring using **Wazuh**, **Sysmon**, **Windows**, and **Ubuntu Linux**.

---

# Lab Overview

This repository demonstrates practical SOC analyst and Detection Engineering skills through real attack simulations, custom Wazuh detection rules, incident investigations, and threat hunting exercises.

The objective of this lab is to simulate realistic attacker behavior, validate endpoint telemetry, build custom detections, and document the investigation process from initial detection through incident response.

---

# Lab Architecture

Windows Endpoint

↓

Microsoft Sysmon

↓

Wazuh Agent

↓

Wazuh Manager (Ubuntu)

↓

Wazuh Dashboard

↓

Threat Hunting & Incident Response

---

# Technologies Used

- Wazuh SIEM
- Microsoft Sysmon
- Windows 11
- Ubuntu Linux
- PowerShell
- XML
- Git & GitHub

---

# Skills Demonstrated

- Detection Engineering
- Threat Hunting
- Incident Response
- Endpoint Monitoring
- SIEM Analysis
- Windows Event Investigation
- Microsoft Sysmon
- PowerShell Analysis
- MITRE ATT&CK Mapping
- Custom Wazuh Rule Development

---

# Repository Structure

```text
attack-simulations/
```

Attack simulations used to generate endpoint telemetry.

```text
custom-rules/
```

Custom Wazuh XML detection rules.

```text
detections/
```

Detection engineering documentation.

```text
incident-reports/
```

Professional incident investigation reports.

```text
threat-hunting/
```

Threat hunting playbooks and investigations.

```text
documentation/
```

Lab setup, installation notes and troubleshooting.

```text
screenshots/
```

Evidence collected from Wazuh and Sysmon.

---

# Detection Engineering

Custom Wazuh detection rules created during this lab:

- PowerShell → Notepad
- PowerShell → CMD
- PowerShell → WScript
- PowerShell → REG
- PowerShell → NET
- PowerShell → Certutil
- PowerShell → Bitsadmin
- PowerShell → Rundll32
- PowerShell → MSHTA
- PowerShell → PsExec

---

# Attack Simulations

Attack simulations include:

- Failed Authentication
- Successful Authentication
- PowerShell Discovery
- Base64 Encoded PowerShell
- Registry Persistence
- LOLBin Execution
- Account Discovery
- Process Creation

---

# Threat Hunting

Threat hunting exercises performed include:

- PowerShell Activity Hunting
- Account Discovery Hunting
- Authentication Hunting
- Process Creation Hunting

---

# Incident Response

Documented incident investigations include:

- Failed Authentication
- PowerShell Discovery
- Encoded PowerShell
- Suspicious PowerShell Activity
- Registry Persistence
- Custom Detection Engineering Alerts
- Windows LOLBin Detection
- Process Creation Investigation

---

# MITRE ATT&CK Coverage

Techniques covered include:

- T1059.001 – PowerShell
- T1087 – Account Discovery
- T1112 – Modify Registry
- T1105 – Ingress Tool Transfer
- T1021.002 – SMB / Windows Admin Shares

---

# Sample Screenshots

Repository includes evidence such as:

- Wazuh Alert Dashboard
- Custom Detection Alerts
- Rule Details
- Sysmon Process Creation Events
- Threat Hunting Queries
- Lab Architecture

---

# Future Improvements

Planned additions include:

- Sigma Rule Development
- YARA Rule Development
- Splunk Detection Engineering
- Elastic SIEM Detection Engineering
- Malware Analysis
- Atomic Red Team Simulations
- ATT&CK Navigator Mapping

---

# Author

**Destiny Israel**

SOC Analyst | Detection Engineering | Threat Hunting | Incident Response

GitHub:
https://github.com/destinyisrael-sec
