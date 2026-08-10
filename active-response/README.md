# AJ SIEM Active Response

This directory documents the automated response actions implemented in the AJ SIEM Home Lab.

The goal of Active Response is to move beyond alert-only monitoring and perform controlled containment actions after high-confidence detections.

## Response Actions

The lab includes Active Response actions such as:

- Temporary source IP blocking
- Suspicious process termination
- DNS tunneling process containment
- Credential dumping process termination
- Malicious persistence removal
- Registry Run Key removal
- Suspicious service removal
- Scheduled task removal
- Ransomware-like artifact quarantine
- Windows Firewall restoration
- Log-clearing evidence preservation

## Response Workflow

**Detection → High-Confidence Alert → Validation → Active Response → Verification**

Response scripts were designed to validate the alert context before performing an action in order to reduce the risk of affecting unrelated processes or files.

## Safety

All response actions were tested inside an isolated VMware lab environment.

No production systems were targeted.
