🔴 Rule 3: Process Creation Monitoring
index=main EventCode=1

Purpose: Logs all processes
Use: Baseline + anomaly detection

🔴 Rule 4: Suspicious Command Execution (cmd)
index=main EventCode=1 CommandLine="*cmd*"

MITRE: T1059
