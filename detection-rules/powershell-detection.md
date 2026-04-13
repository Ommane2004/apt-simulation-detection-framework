🔴 Rule 1: Suspicious PowerShell Execution
index=main EventCode=1 CommandLine="*powershell*"

Description: Detects PowerShell usage
MITRE ATT&CK: T1059
Severity: High

🔴 Rule 2: Encoded PowerShell Command
index=main EventCode=1 CommandLine="*-enc*" OR CommandLine="*EncodedCommand*"

Why dangerous: Attackers hide payloads
MITRE: T1059

🔴 Rule 3: Process Creation Monitoring

Create file:
👉 process-creation.md

index=main EventCode=1

Purpose: Logs all processes
Use: Baseline + anomaly detection

🔴 Rule 4: Suspicious Command Execution (cmd)
index=main EventCode=1 CommandLine="*cmd*"

MITRE: T1059

🔴 Rule 5: Network Connections 🌐

👉 network-activity.md

index=main EventCode=3

Detects:

Outbound connections
Possible C2 communication

MITRE: T1043

🔴 Rule 6: Suspicious External IP
index=main EventCode=3 NOT dest_ip="192.168.*"

Purpose: Detect external traffic
Use: C2 detection

🔴 Rule 7: Registry Persistence

👉 persistence-detection.md

index=main EventCode=13

Detects:

Startup persistence
MITRE: T1547
🔴 Rule 8: File Creation Activity
index=main EventCode=11

Use:

Detect malware drop
🔴 Rule 9: Lateral Movement

👉 lateral-movement.md

index=main EventCode=3 dest_port=3389

Detects:

RDP connections

MITRE: T1021

🔴 Rule 10: Privilege Enumeration
index=main EventCode=1 CommandLine="*whoami*"
🔴 Rule 11: Suspicious Parent-Child Process
index=main EventCode=1 ParentImage="*powershell.exe*" Image="*cmd.exe*"

🔥 VERY IMPORTANT rule (interview favorite)

🔴 Rule 12: Data Exfiltration (Large Transfer Pattern)
index=main EventCode=3 | stats count by dest_ip

Detects:

Repeated outbound traffic
🔴 Rule 13: PowerShell + Network Combo
index=main EventCode=1 CommandLine="*Invoke-WebRequest*"
