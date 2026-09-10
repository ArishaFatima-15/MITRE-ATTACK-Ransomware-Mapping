# MITRE ATT&CK Mapping Exercise: Ransomware Incident Analysis

## Project Overview:
This project presents a structured Security Operations Center (SOC) threat analysis of the incident **"128 Seconds to Disruption: Microsoft Defender Stops Ransomware at QNET"**. The primary goal is to map the attack lifecycle against the **MITRE ATT&CK Framework**, identify crucial detection points, and visualize threat activity using the MITRE ATT&CK Navigator.

## MITRE ATT&CK Mapping Matrix:

| Attack Stage | MITRE Tactic | Technique Name | MITRE ATT&CK ID |
| :--- | :--- | :--- | :--- |
| Malicious file opened by user | Initial Access / Execution | Phishing / User Execution: Malicious File | `T1566` / `T1204.002` |
| `mshta.exe` executed by malicious file | Stealth | System Binary Proxy Execution: Mshta | `T1218.005` |
| `mshta.exe` connected to C2 URL | Command and Control | Application Layer Protocol: Web Protocols | `T1071.001` |
| Second-stage payload execution | Execution | Command and Scripting Interpreter | `T1059` |
| RunMRU registry activity observed | Persistence | Modify Registry | `T1112` |

---

## Detection Opportunities & Security Control:

* **Initial Access:** Email Security Gateway, Microsoft Defender SmartScreen, Secure Web Gateway.
* **Proxy Execution (`mshta.exe`):** Microsoft Defender for Endpoint (EDR), Process Monitoring, Application Control (AppLocker/WDAC).
* **Command & Control:** Firewall, IDS/IPS, DNS Monitoring, Proxy Logs, Network Traffic Monitoring.
* **Payload Execution:** Network Detection and Response (NDR), Web Proxy Monitoring.
* **Persistence:** Registry Monitoring, Windows Event Logs (Sysmon), EDR, SIEM Correlation Rules.

---

## Incident Summary:
The attack began via a malicious file delivered through email or web link. The file leveraged `mshta.exe` to connect to an attacker-controlled infrastructure and retrieve a second-stage payload. Persistence was attempted via RunMRU registry modifications. Microsoft Defender automatically contained the threat within 128 seconds, preventing lateral movement or organizational damage.

---

## Files:

* [Arisha_Fatima_MITRE_ATTCK_Mapping_Exercise.pdf](Arisha_Fatima_MITRE_ATTCK_Mapping_Exercise.pdf) — Complete Analysis Report & MITRE ATT&CK Documentation
* [microsoft_defender_ransomware_incident_mapping.pdf](microsoft_defender_ransomware_incident_mapping.pdf) — Complete Analysis Report & MITRE ATT&CK Documentation
