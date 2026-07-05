# Microsoft Sentinel Analytics Rules

This folder contains Microsoft Sentinel analytics rule templates used in the security operations lab.

Each rule includes:

- Rule name
- Description
- Severity
- Query frequency
- Query period
- MITRE ATT&CK mapping
- Data source requirements
- Entity mappings
- False positive guidance
- Response actions
- Related playbooks and detections

## Current Rules

| Rule | Purpose | Related Detection | Related Playbook |
|---|---|---|---|
| `malicious-url-clicked.yaml` | Detect users who clicked suspicious or malicious URLs from email | `detections/email/malicious-url-clicked.kql` | `playbooks/phishing-user-clicked-url.md` |
