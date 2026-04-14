🚀 APT Simulation & Detection Framework
📌 What This Project Is

This project is a hands-on cybersecurity lab that simulates real-world attacker behavior and detects it using a centralized logging and monitoring system.

It replicates how a Security Operations Center (SOC) works by combining attack simulation with real-time detection using Splunk.

🎯 Problem Statement

Modern cyberattacks are stealthy and multi-stage. Traditional security tools often fail to detect them in real time.

This project solves that problem by:

Generating detailed system logs using Sysmon
Centralizing logs using Splunk
Creating detection rules for suspicious activity
Visualizing threats using dashboards

🧱 High-Level Architecture

[Windows System + Sysmon]
          
          ↓
          
[Universal Forwarder]
          
          ↓
          
[Splunk Server (Ubuntu)]
          
          ↓
          
[Detection Rules]
          
          ↓
          
[Alerts + Dashboards]

🔍 What This Project Covers
Attack simulation (PowerShell, CMD)
Log collection using Sysmon
Log forwarding using Universal Forwarder
Detection using Splunk SPL queries
Alert creation
Dashboard visualization
🛠️ Tools Used
Splunk Enterprise
Splunk Universal Forwarder
Sysmon
VMware Lab
Windows 10 + Ubuntu
⚔️ Attack Simulation Summary

Simulated activities include:

PowerShell execution
Command prompt activity
Process creation events
Network connections
🚨 Detection Summary

Example detection rule:

index=main EventCode=1 CommandLine="*powershell*"

Detects suspicious PowerShell execution using Sysmon logs.

📊 Output
Logs successfully collected and indexed
Detection rules triggered alerts
Dashboard created for visualization
SOC-style monitoring implemented
🔗 Related Sections
Scope & Objectives → scope-and-objectives.md
Defender Mindset → defender-first-mindset.md
Ethical Considerations → ethical-and-legal-considerations.md

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/8c4281b2-e147-4719-8930-61588e61d4da" />



