🔍 Detection Logic
📌 Overview

This project follows a log-based detection approach using Sysmon and Splunk.
Instead of relying on signatures, detection is based on analyzing system behavior through logs.

All activities are captured using Sysmon and analyzed in Splunk using SPL (Search Processing Language) queries.

🧠 Detection Strategy

The detection logic is based on:

Monitoring process execution
Analyzing command-line activity
Tracking network connections
Identifying abnormal behavior patterns

👉 Focus: Behavior-based detection

⚙️ Log Sources
Source	Description
Sysmon Event ID 1	Process Creation
Sysmon Event ID 3	Network Connections
Sysmon Event ID 13	Registry Changes
🚨 Detection Rules
🔴 1. PowerShell Execution Detection
index=main EventCode=1 CommandLine="*powershell*"
📌 Purpose:

Detects PowerShell usage, commonly used in attacks.

🧠 Why Suspicious:

Attackers often use PowerShell to execute malicious scripts.

🎯 MITRE ATT&CK:

T1059 – Command and Scripting Interpreter

🔴 2. Encoded Command Detection
index=main EventCode=1 CommandLine="*-enc*" OR CommandLine="*EncodedCommand*"
📌 Purpose:

Detects obfuscated PowerShell commands.

🧠 Why Suspicious:

Attackers encode commands to bypass detection.

🎯 MITRE:

T1027 – Obfuscated Files or Information

🔴 3. Command Prompt Activity
index=main EventCode=1 CommandLine="*cmd*"
📌 Purpose:

Detects command prompt usage.

🧠 Why Suspicious:

Used for executing system commands.

🔴 4. Network Activity Detection
index=main EventCode=3
📌 Purpose:

Detects outbound network connections.

🧠 Why Suspicious:

May indicate communication with external servers (C2).

🎯 MITRE:

T1071 – Application Layer Protocol

🔴 5. Registry Persistence Detection
index=main EventCode=13
📌 Purpose:

Detects registry changes.

🧠 Why Suspicious:

Attackers use registry keys for persistence.

🎯 MITRE:

T1547 – Boot or Logon Autostart Execution

🔴 6. Suspicious Parent-Child Process
index=main EventCode=1 ParentImage="*cmd.exe" Image="*powershell.exe"
📌 Purpose:

Detects unusual process relationships.

🧠 Why Suspicious:

CMD launching PowerShell may indicate malicious activity.

🔄 Detection Workflow
Command Execution → Sysmon Log → Forwarder → Splunk Index
→ Detection Query → Alert → Dashboard Visualization
📊 Visualization & Alerting

Detection rules are used to:

Trigger alerts for suspicious behavior
Populate dashboard panels
Provide real-time monitoring
📸 Screenshot Example
![Detection](../screenshots/detection.png)

👉 Add your Splunk query result screenshot here

🧠 Key Takeaways
Detection is based on behavior, not signatures
Sysmon provides deep system visibility
Splunk enables powerful log analysis
Combining logs + queries = effective threat detection
