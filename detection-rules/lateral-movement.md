🔴 Rule 9: Lateral Movement
index=main EventCode=3 dest_port=3389

Detects:

RDP connections

MITRE: T1021

🔴 Rule 10: Privilege Enumeration
index=main EventCode=1 CommandLine="*whoami*"
🔴 Rule 11: Suspicious Parent-Child Process
index=main EventCode=1 ParentImage="*powershell.exe*" Image="*cmd.exe*"

🔴 Rule 12: Data Exfiltration (Large Transfer Pattern)
index=main EventCode=3 | stats count by dest_ip

Detects:

Repeated outbound traffic
🔴 Rule 13: PowerShell + Network Combo
index=main EventCode=1 CommandLine="*Invoke-WebRequest*"
