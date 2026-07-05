# Email Security Detections

This folder contains KQL detections for Microsoft Defender XDR and Microsoft Sentinel scenarios related to email security.

## Current Detections

| Detection | Purpose | Related Playbook |
|---|---|---|
| `malicious-url-clicked.kql` | Detect users who clicked suspicious or malicious URLs from email | `playbooks/phishing-user-clicked-url.md` |

## Main Data Sources

- `EmailEvents`
- `UrlClickEvents`
- Defender for Office 365 alerts
- Microsoft Sentinel incidents

## Analyst Questions

These detections help answer:

1. Who received the suspicious email?
2. Who clicked the URL?
3. Was the click blocked or allowed?
4. Was the email delivered to inbox, junk, or quarantine?
5. Was the message part of a larger phishing campaign?
