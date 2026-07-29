# Threat Hunt 002 - Windows Registry Persistence Investigation

## Objective

Investigate registry modifications that may indicate persistence techniques used by attackers.

---

## Hunt Hypothesis

Attackers commonly establish persistence by modifying Windows Registry Run Keys so malicious programs execute automatically after user logon.

This hunt validates Wazuh's ability to detect registry activity.

---

## Environment

SIEM
- Wazuh

Endpoint
- Windows 11
- Sysmon

---

## Hunt Query

Search Term

registry

Rule ID

597

---

## Investigation

Observed Activity

✔ Registry Key Entry Deleted

Multiple registry modification events were detected by Wazuh during endpoint monitoring.

The events demonstrated that registry modifications were successfully collected and correlated.

---

## MITRE ATT&CK

T1112 — Modify Registry

Persistence

Defense Evasion

---

## Evidence

Observed Rule

597

Severity

5

Manager

computerguy-VirtualBox

Agent

DESKTOP-3K70H54

---

## Findings

The endpoint generated registry modification events that could indicate persistence activity.

Although these events originated from a controlled lab environment, the same detection logic is applicable to real-world investigations involving malware persistence.

---

## Skills Demonstrated

- Threat Hunting
- Registry Analysis
- Endpoint Monitoring
- Wazuh Investigation
- MITRE ATT&CK Mapping
- Windows Forensics

---

## Screenshots

- Registry Event Search
- Rule 597 Details

---

## Outcome

Successfully validated registry monitoring capabilities within Wazuh and demonstrated investigation of Windows persistence-related activity.
