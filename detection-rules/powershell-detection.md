🔴 Rule 1: Suspicious PowerShell Execution
index=main EventCode=1 CommandLine="*powershell*"

Description: Detects PowerShell usage
MITRE ATT&CK: T1059
Severity: High

🔴 Rule 2: Encoded PowerShell Command
index=main EventCode=1 CommandLine="*-enc*" OR CommandLine="*EncodedCommand*"

Why dangerous: Attackers hide payloads
MITRE: T1059
