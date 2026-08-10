# AJ SIEM — Security Use Cases

This document summarizes the 20 detection and response use cases implemented and tested in the AJ SIEM Home Lab.

| # | Use Case | Security Focus | MITRE ATT&CK |
|---|---|---|---|
| 01 | RDP Brute Force | Authentication Attacks | T1110 |
| 02 | SQL Injection | Web Application Attack | T1190 |
| 03 | Directory Traversal | Web Application Attack | T1190 |
| 04 | Suspicious Outbound C2 | Command & Control | T1071.001 |
| 05 | DNS Tunneling | Command & Control | T1071.004 |
| 06 | IIS Web Shell | Persistence | T1505.003 |
| 07 | IIS Worker Spawning PowerShell/CMD | Command Execution | T1059 |
| 08 | Mimikatz / Credential Dumping | Credential Access | T1003 |
| 09 | SAM/SYSTEM Credential Dumping | Credential Access | T1003.002 |
| 10 | Encoded PowerShell | Command Execution | T1059.001 |
| 11 | Suspicious Binary Download | Command & Control | T1105 |
| 12 | MSHTA Execution | Defense Evasion | T1218.005 |
| 13 | Ransomware-like Behavior | Impact | T1486 |
| 14 | Unauthorized Local User Creation | Persistence | T1136.001 |
| 15 | User Added to Administrators | Privilege Escalation | T1098 |
| 16 | Scheduled Task Persistence | Persistence | T1053.005 |
| 17 | Suspicious Windows Service | Persistence | T1543.003 |
| 18 | Registry Run Key Persistence | Persistence | T1547.001 |
| 19 | Windows Firewall Disabled | Defense Evasion | T1562.004 |
| 20 | Windows Event Logs Cleared | Defense Evasion | T1070.001 |

## Detection & Response Approach

The use cases were designed around the following SOC workflow:

**Activity → Log Collection → Detection → Alert → Investigation → Active Response → Validation**

Detection sources included:

- Sysmon
- Windows Event Logs
- IIS Logs
- Wazuh File Integrity Monitoring
- Network activity
- Custom Wazuh detection rules

Several high-confidence detections were connected to Active Response actions such as process termination, IP blocking, persistence removal, artifact quarantine, security control restoration, and evidence preservation.

> All scenarios were performed inside an isolated virtual lab for educational and defensive security purposes.
