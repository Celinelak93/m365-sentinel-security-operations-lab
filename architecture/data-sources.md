# Security Data Sources

## Purpose

This document lists the major security data sources used in the lab and explains what each source contributes to detection and investigation.

| Data Source | Tool | Security Value |
|---|---|---|
| Sign-in logs | Microsoft Entra ID | Detect suspicious login behavior, risky users, impossible travel, and failed authentication patterns |
| Audit logs | Microsoft Entra ID / Microsoft 365 | Track administrative activity, policy changes, mailbox changes, and suspicious configuration updates |
| Email events | Defender for Office 365 | Investigate phishing, malicious attachments, malicious URLs, and email delivery patterns |
| URL click events | Defender for Office 365 | Identify users who clicked suspicious or malicious links |
| Device process events | Defender for Endpoint | Detect suspicious command execution, PowerShell abuse, LOLBins, malware, and ransomware behavior |
| Device network events | Defender for Endpoint | Investigate suspicious outbound connections, C2 activity, and connections to malicious domains |
| Cloud app activity | Defender for Cloud Apps | Detect risky OAuth apps, mass downloads, shadow IT, and unusual SaaS behavior |
| Sentinel incidents | Microsoft Sentinel | Centralize alerts, incidents, investigation workflow, and response automation |
