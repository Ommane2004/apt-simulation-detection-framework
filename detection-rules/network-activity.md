🔴 Rule 5: Network Connections 🌐
index=main EventCode=3

Detects:

Outbound connections
Possible C2 communication

MITRE: T1043

🔴 Rule 6: Suspicious External IP
index=main EventCode=3 NOT dest_ip="192.168.*"

Purpose: Detect external traffic
Use: C2 detection
