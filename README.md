# Windows Sysmon Detection Lab

This repository contains a custom Windows Endpoint Detection Lab built to analyze system activity, understand attacker behavior, and build SOC-level detection skills. The project uses Sysmon to generate rich telemetry from Windows systems and organizes the data across multiple event categories for investigation and detection engineering.

---

## 🔍 Project Goal

The goal of this lab is to create a realistic endpoint-monitoring environment where I can:

- Collect detailed Windows event telemetry  
- Analyze attacker behavior and system activity  
- Build and test detection rules  
- Simulate attacks and review corresponding logs  
- Strengthen SOC investigation skills  
- Experiment with SIEM integration and alerting  

This project represents my hands-on effort to build a complete detection environment from scratch.

---


---

## 🛠️ Setup Instructions

### **1. Install Sysmon**

Download Sysmon from Microsoft Sysinternals.

Install with my config:
Sysmon64.exe -accepteula -i sysmonconfig.xml

### **2. Verify Telemetry**
Open:
Event Viewer > Applications and Services Logs
> Microsoft > Windows > Sysmon > Operational

You should now see detailed logs for process execution, network events, registry modifications, and more.

---

## 🧪 Attack Simulation Scenarios

I used multiple simulation techniques to generate telemetry:

- Nmap port scanning  
- Brute-force attempt logs  
- Suspicious PowerShell execution  
- Remote thread injection demo  
- Mimikatz-style behavior simulation  
- File creation & deletion events  
- Registry-based persistence lab  
- WMI execution experiment  

Each attack type helps validate the quality and usefulness of Sysmon rules.

---

## 🔍 Custom Detection Logic

Inside `custom_detections/`, I added my own rules for:

- Suspicious parent-child process chains  
- Encoded PowerShell commands  
- Abnormal process access patterns  
- Potential persistence modifications  
- Network anomalies  
- Rare or dangerous executables  

These detections help convert raw logs into actionable SOC alerts.

---

## 📚 Analysis Notes

The `analysis/` directory contains my investigation notes and breakdowns of Sysmon event patterns, including:

- How attackers commonly abuse Windows binaries  
- Identifying red flags in process creation  
- Correlating network events with suspicious actions  
- Registry changes linked to persistence  
- Pipe and WMI usage linked to lateral movement  

These notes show real analyst-style thinking and investigation workflow.

---

## 🛡️ MITRE ATT&CK Mapping

`attack_matrix/` maps Sysmon event types to ATT&CK techniques, including:

- **T1059** – Command Execution  
- **T1047** – WMI Execution  
- **T1547** – Registry Persistence  
- **T1021** – Remote Services  
- **T1053** – Scheduled Tasks  
- **T1105** – Ingress/Egress Tool Transfer  

This helps build intuition about which Sysmon logs map to specific attack behaviors.

---

## 📡 SIEM Integration (Optional)

The logs generated from this lab can be integrated into:

- **Wazuh SIEM**
- **Elastic Stack (ELK)**
- **Splunk**
- **Microsoft Sentinel**

Using Winlogbeat or the Wazuh agent, the Sysmon logs can be forwarded to generate detections and dashboards.

---

## 👤 Author

**Divakar (Diva07-kd)**  
Cybersecurity & SOC Enthusiast  
Focused on Endpoint Detection, Windows Security, and Detection Engineering.

If this project helped you, consider starring the repo!



