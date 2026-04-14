🎯 Scope and Objectives

📌 Project Scope

This project focuses on building a controlled cybersecurity lab environment to simulate attacker behavior and detect it using centralized logging and monitoring.

The scope includes:

Setting up a Windows system with Sysmon for log generation
Configuring Splunk Universal Forwarder to collect logs
Deploying a Splunk Server (Ubuntu) for log analysis
Simulating basic attack techniques (PowerShell, CMD)
Creating detection rules using Splunk SPL queries
Generating alerts for suspicious activity
Building dashboards for visualization

⚙️ Environment Scope

The project is implemented in a virtual lab environment:

VMware-based setup
Windows 10 (Target Machine)
Ubuntu Server (Splunk Server)
Isolated network for safe testing

⚔️ Attack Simulation Scope

The project simulates basic attacker behaviors such as:

PowerShell execution
Command Prompt usage
Process creation events
Simple network activity

⚠️ Note:
Advanced attack techniques like lateral movement, persistence, and exploitation are not included in this project.

🔍 Detection Scope

Detection capabilities include:

Monitoring Sysmon Event ID 1 (Process Creation)
Monitoring Sysmon Event ID 3 (Network Connection)
Detecting suspicious command-line activity
Identifying PowerShell execution
🚫 Limitations

This project has the following limitations:

Limited to a lab environment (not production-level SOC)
Focuses on basic attack detection only
No automated incident response implemented
No integration with external threat intelligence
🎯 Objectives
🎯 Primary Objective

To design and implement a real-time attack detection system using Splunk and Sysmon in a simulated environment.

🎯 Secondary Objectives
To understand how attackers execute commands
To generate and analyze system logs
To build detection rules using Splunk
To create alerts for suspicious activities
To visualize security events using dashboards
🎯 Learning Objectives
Gain hands-on experience with SIEM (Splunk)
Understand log-based detection techniques
Learn Sysmon configuration and usage
Develop a SOC analyst mindset
Map attacker behavior to detection rules
🎯 Outcome Objectives

By completing this project:

A functional detection system is implemented
Suspicious activities can be identified in real time
Alerts are triggered for potential threats
Dashboards provide visibility into system activity
