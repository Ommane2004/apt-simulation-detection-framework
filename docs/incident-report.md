🚨 Incident Report
📌 Incident Summary

A suspicious PowerShell execution was detected on the monitored Windows system through Splunk alerts.

The activity was flagged as potentially malicious due to unusual command-line usage and process behavior.

🕒 Date & Time
Date: (Add your date)
Time: (Add time from Splunk logs)
🖥️ Affected System
Host: Windows Machine
Log Source: Sysmon
SIEM: Splunk
🔍 Detection Details

The alert was triggered using the following Splunk query:

index=main EventCode=1 CommandLine="*powershell*"

This query identifies PowerShell execution events captured by Sysmon.

📸 Evidence
![Alert](../screenshots/alerts.png)
![Logs](../screenshots/logs.png)

👉 Add:

Alert triggered screenshot
Log details screenshot
🧠 Investigation Steps
Verified alert in Splunk dashboard
Checked EventCode 1 logs for process creation
Analyzed command-line arguments
Identified PowerShell execution
Confirmed activity was part of simulated attack
⚠️ Indicators of Compromise (IOCs)
Process: powershell.exe
Event ID: 1
CommandLine: Suspicious execution pattern
🎯 Impact Analysis
No real system compromise occurred
Activity was part of controlled simulation
Demonstrates potential attack vector
🛠️ Response Actions
Alert successfully triggered
Activity logged and analyzed
No remediation required (lab environment)
🔄 Lessons Learned
PowerShell is a critical attack vector
Monitoring process creation is essential
Sysmon logs provide valuable visibility
Detection rules must be continuously improved
📊 Final Status

✅ Incident detected
✅ Logs analyzed
✅ Alert triggered
✅ System behavior understood
