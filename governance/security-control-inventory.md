# Security Control Inventory

## Purpose

This document maps major organizational asset areas to security tools, common risks, existing controls, detection coverage, control gaps, and recommended improvements.

The goal is to demonstrate how a security operations team can understand current coverage, identify weaknesses, and build a practical security roadmap.

## Control Inventory

| Security Area | Assets Covered | Main Microsoft Tools | Key Risks | Example Controls | Detection Coverage | Gaps | Recommended Improvements |
|---|---|---|---|---|---|---|---|
| Identity | Users, admins, service accounts | Microsoft Entra ID, Conditional Access, PIM, Defender XDR | Account compromise, MFA fatigue, impossible travel, privilege abuse | MFA, Conditional Access, privileged role review, sign-in risk policies | Risky sign-ins, impossible travel, admin login from unusual location | Inconsistent CA policies, limited privileged access review | Standardize CA policies, enable PIM, review admin roles monthly |
| Endpoint | Laptops, desktops, servers | Defender for Endpoint, Intune | Malware, ransomware, PowerShell abuse, vulnerable software | EDR, antivirus, attack surface reduction rules, disk encryption | Suspicious PowerShell, malware alerts, ransomware behavior | Some endpoints not onboarded, weak ASR rule coverage | Onboard all endpoints, enforce ASR rules, monitor device exposure score |
| Email | Mailboxes, inbound/outbound email | Defender for Office 365, Exchange Online Protection | Phishing, malicious URLs, malicious attachments, impersonation | Safe Links, Safe Attachments, anti-phishing policies, quarantine | Malicious URL clicks, phishing campaign detection, suspicious inbox rules | Weak impersonation protection, inconsistent quarantine review | Tune anti-phishing policies, monitor clicked malicious URLs, review mailbox rules |
| Collaboration | Teams, SharePoint, OneDrive | Defender for Office 365, Purview DLP, SharePoint Admin Center | Oversharing, malicious files, external guest abuse | Safe Attachments, DLP, sensitivity labels, guest access control | Malicious file detection, external sharing events | Anonymous sharing allowed, weak guest lifecycle review | Restrict anonymous sharing, apply sensitivity labels, review external users |
| Cloud/SaaS | SaaS apps, OAuth apps, cloud services | Defender for Cloud Apps, Entra ID, Sentinel | Shadow IT, risky OAuth consent, data exfiltration | App discovery, OAuth app governance, session controls | Suspicious OAuth app consent, mass download activity | No recurring OAuth app review | Create SaaS governance process, review risky apps monthly |
| Network | VPN, firewall, DNS, internet traffic | Firewall logs, Sentinel, Defender for Endpoint | C2 traffic, suspicious DNS, unauthorized access | Firewall rules, DNS filtering, VPN access control | Suspicious outbound connections, known malicious domains | Limited central log collection | Send firewall/DNS/VPN logs to Sentinel |
| Vulnerability Management | Endpoints, servers, applications | Defender Vulnerability Management, Intune | Unpatched software, exposed services, weak configurations | Vulnerability scanning, patch management, secure configuration baseline | High-risk vulnerability alerts, exposed device score | No formal remediation SLA | Define patch SLAs, prioritize critical vulnerabilities, track remediation |
| Security Operations | Alerts, incidents, investigations | Microsoft Sentinel, Defender XDR | Alert fatigue, missed incidents, slow response | Incident queue, analytics rules, playbooks, escalation process | Sentinel incidents, Defender alerts, KQL hunting | No formal triage process | Define severity levels, response playbooks, SOC KPIs |


## Priority Gaps

The most important security gaps are:

1. Inconsistent Conditional Access coverage
2. Limited privileged access management
3. Weak monitoring of malicious URL clicks
4. Incomplete endpoint onboarding
5. Lack of recurring OAuth/SaaS app review
6. No formal incident response playbook library
7. No clear security roadmap based on control gaps

## 90-Day Improvement Roadmap

| Timeline | Priority | Action | Expected Outcome |
|---|---|---|---|
| Days 1-30 | Identity | Review Conditional Access and privileged accounts | Reduce account compromise risk |
| Days 1-30 | Email | Improve phishing and malicious URL click monitoring | Faster response to user-clicked threats |
| Days 31-60 | Endpoint | Validate Defender onboarding and ASR coverage | Better endpoint detection and prevention |
| Days 31-60 | SOC | Create incident response playbooks | Standardized investigation and response |
| Days 61-90 | Governance | Build NIS2/control mapping | Better compliance and management reporting |
| Days 61-90 | Cloud/SaaS | Review risky OAuth apps and shadow IT | Reduce SaaS and third-party app risk |
