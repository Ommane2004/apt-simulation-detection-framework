🛡️ Advanced Persistent Threat Simulation & Detection Framework (APT-SIM)

A hands-on cybersecurity lab that simulates real-world APT attacks and detects them using SIEM (Splunk), Sysmon, and threat intelligence techniques.

📌 Project Overview

The APT-SIM Framework is designed to simulate multi-stage cyber attacks and analyze them from a Blue Team perspective.

It replicates the full attack lifecycle:

🔴 Initial Access → ⚡ Execution → 🧠 Persistence → 🌐 Lateral Movement → 📦 Data Exfiltration → 🔍 Detection

This project demonstrates how modern attackers operate and how defenders can detect and respond effectively.

🎯 Objectives
Simulate real-world APT attack scenarios safely
Collect logs using Sysmon & Universal Forwarder
Detect malicious activity using Splunk SIEM
Create dashboards for SOC visibility
Generate alerts for suspicious behavior
Map activities to MITRE ATT&CK framework
🧠 Architecture



![Architecture](./architecture.png)

💡 Diagram includes:

Kali Linux (Attacker)
Windows 10 (Victim)
Ubuntu Server (Splunk Server)
Universal Forwarder + Sysmon
🏗️ Lab Setup
Component	Technology
Attacker Machine	Kali Linux
Target Machine	Windows 10
SIEM Server	Ubuntu + Splunk
Log Collection	Sysmon + Splunk Forwarder
Virtualization	VMware
⚙️ Installation & Setup
1️⃣ Install Splunk Server (Ubuntu)
sudo /opt/splunk/bin/splunk start
2️⃣ Install Universal Forwarder (Windows)
Install Splunk Universal Forwarder
Configure receiving indexer
splunk add forward-server <SPLUNK_IP>:9997
3️⃣ Configure Sysmon
sysmon64.exe -i sysmonconfig.xml
4️⃣ Configure Log Inputs

Collect logs:

Windows Event Logs
Sysmon Logs
🔴 Attack Simulation (Safe Lab)
Execution Simulation
powershell -ExecutionPolicy Bypass
Process Creation
notepad.exe
calc.exe
Network Activity
ping google.com
🔍 Detection Techniques
Splunk Queries
# Process creation
index=main EventCode=1

# PowerShell detection
index=main EventCode=1 CommandLine="*powershell*"

# Network activity
index=main EventCode=3

# Registry changes
index=main EventCode=13
🚨 Alerting

Example Alert:

Name: Suspicious PowerShell Execution
Condition: EventCode=1 AND CommandLine contains powershell
Trigger: When results > 0
📊 Dashboard

Features:

PowerShell activity monitoring
Process creation tracking
Network connections visualization
Alert monitoring panel

👉 Add screenshot:

![Dashboard](./dashboard.png)
🧪 Attack Scenario
User executes PowerShell command
Suspicious process created
Network connection initiated
Logs captured via Sysmon
Splunk detects anomaly
Alert triggered
📈 Results
Successfully detected PowerShell activity
Generated alerts in real-time
Visualized attack behavior in dashboard
Created SOC-level monitoring system
🧠 MITRE ATT&CK Mapping
Technique	ID
PowerShell Execution	T1059
Process Creation	T1055
Command Execution	T1059
Network Connection	T1043
🔮 Future Enhancements
Integrate ELK Stack
Add AI-based anomaly detection
Automate attack simulation
Implement SOAR integration
⚠️ Disclaimer

This project is created for educational and ethical purposes only.
All simulations were performed in a controlled lab environment.

👨‍💻 Author

CyberKing 👑
Aspiring Cybersecurity Analyst | SOC Enthusiast | Future Red Teamer
