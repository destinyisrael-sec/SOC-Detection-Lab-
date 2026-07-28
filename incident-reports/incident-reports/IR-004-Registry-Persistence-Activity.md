# Incident Report 004 – Registry Persistence Activity

## Summary

A Windows endpoint generated multiple alerts related to registry key modifications. Wazuh detected registry key deletion activity, indicating possible persistence modification or cleanup behavior commonly associated with malware or attacker actions.

---

## Detection Summary

Date:
July 27, 2026

Agent:
DESKTOP-3K70H54

Rule ID:
597

Rule Level:
5

Rule Description:
Registry Key Entry Deleted

---

## Investigation

During endpoint monitoring, Wazuh generated multiple alerts showing registry key deletion events.

Registry modifications are commonly associated with:

- Malware persistence
- Startup program modifications
- Registry cleanup after execution
- Defensive or attacker removal of persistence mechanisms

The rule triggered repeatedly, confirming that registry activity was successfully monitored by the Wazuh agent.

---

## MITRE ATT&CK Mapping

Technique:
T1112 – Modify Registry

Tactic:
Defense Evasion

Potential Persistence Activity

---

## Evidence

See screenshots:

- Registry alert list
- Registry rule details

---

## Analyst Assessment

The activity demonstrates successful monitoring of Windows Registry modifications.

Although this simulation generated registry deletion events instead of registry creation events, the detection confirms that Wazuh is successfully collecting and analyzing registry activity from the Windows endpoint.

No evidence of an active compromise was identified during the investigation.

---

## Skills Demonstrated

- Threat Hunting
- Windows Registry Analysis
- Endpoint Monitoring
- Detection Engineering
- SIEM Investigation
- MITRE ATT&CK Mapping
- Incident Documentation
