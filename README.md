# apt-simulation-detection-framework
Advanced Persistent Threat Simulation using Splunk, Sysmon, and SIEM techniques for real-time threat detection

🧠 Overview

This project demonstrates a complete SIEM-based lab for simulating and detecting Advanced Persistent Threat (APT) attacks using Splunk and Sysmon.

⚙️ Architecture
Windows Machine → Sysmon
Splunk Universal Forwarder
Splunk Server (Ubuntu)
⚔️ Attack Simulation

The following attack techniques were simulated:

PowerShell execution
Encoded commands
Registry persistence
Network activity
🔍 Detection Techniques
Technique	Detection
PowerShell Execution	EventCode=1
Encoded Commands	CommandLine filter
Persistence	EventCode=13
Network Activity	EventCode=3
📊 Dashboard

A real-time monitoring dashboard was created in Splunk to visualize:

Process activity
Network connections
Persistence mechanisms
🚨 Alerts

Alerts were configured to detect suspicious activity such as:

PowerShell execution
Encoded commands
Registry changes
🧠 Key Learnings
SIEM implementation
Log analysis
Threat detection
Attack simulation
📸 Screenshots

(Add your images here)
