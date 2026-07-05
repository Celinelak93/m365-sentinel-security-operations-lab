# NIS2 Readiness Mapping

## Purpose

This document maps practical cybersecurity controls to NIS2-style governance expectations.

The goal is not to provide legal advice. The goal is to show how a security operations team can translate cybersecurity requirements into practical controls, evidence, monitoring, and improvement actions.

## Governance Mapping

| NIS2 / Governance Area | Practical Security Control | Microsoft Tooling | Evidence / Artifact | Project File |
|---|---|---|---|---|
| Cybersecurity risk management | Maintain a security control inventory by asset area | Microsoft Defender XDR, Sentinel, Entra ID | Security control inventory | `governance/security-control-inventory.md` |
| Incident handling | Create incident response playbooks for common scenarios | Sentinel, Defender XDR | Phishing response playbook | `playbooks/phishing-user-clicked-url.md` |
| Detection capability | Build analytics rules for high-risk scenarios | Sentinel, Defender XDR | KQL detections and Sentinel rule templates | `detections/email/malicious-url-clicked.kql` |
| Business continuity | Define response actions for containment and recovery | Sentinel, Defender XDR, Intune | Recovery steps in playbooks | `playbooks/phishing-user-clicked-url.md` |
| Supply chain / third-party risk | Review SaaS apps, OAuth permissions, and external sharing | Defender for Cloud Apps, Entra ID, Purview | SaaS review checklist | Future file |
| Access control | Enforce MFA, Conditional Access, and privileged access review | Entra ID, Conditional Access, PIM | Identity control review | `governance/security-control-inventory.md` |
| Asset visibility | Track users, endpoints, mailboxes, SaaS apps, and cloud services | Defender XDR, Sentinel, Intune | Asset coverage matrix | `governance/security-control-inventory.md` |
| Vulnerability management | Identify and remediate high-risk vulnerabilities | Defender Vulnerability Management, Intune | Patch/remediation tracker | Future file |
| Security monitoring | Centralize logs and alerts into a SOC workflow | Sentinel, Defender XDR | SOC KPI dashboard | `dashboards/soc-kpi-dashboard.md` |
| Management reporting | Summarize incidents in business-risk language | Sentinel, dashboards, reports | Executive incident report | `dashboards/executive-incident-report.md` |
| Continuous improvement | Review incidents and close control gaps | Sentinel, Defender XDR, governance process | 90-day roadmap | `governance/security-control-inventory.md` |

## Readiness Assessment

| Area | Current Lab Coverage | Maturity Level | Notes |
|---|---|---|---|
| Security control inventory | Covered | Medium | Asset areas and control gaps are documented |
| Incident response playbooks | Partially covered | Medium | Phishing playbook exists; more scenarios should be added |
| Detection engineering | Partially covered | Medium | Malicious URL click detection exists; identity and endpoint detections should be added |
| Sentinel analytics rules | Partially covered | Medium | One rule template exists |
| Executive reporting | Covered | Medium | Executive incident report exists |
| SOC metrics | Covered | Medium | KPI dashboard exists |
| Identity governance | Partially covered | Low-Medium | Needs dedicated Conditional Access and PIM review file |
| Vulnerability management | Not yet covered | Low | Needs vulnerability remediation workflow |
| SaaS/OAuth governance | Not yet covered | Low | Needs cloud app governance checklist |
| Supplier risk | Not yet covered | Low | Needs third-party risk checklist |

## Priority Gaps

The most important governance gaps are:

1. No dedicated identity governance checklist
2. No vulnerability remediation workflow
3. No SaaS/OAuth application review process
4. No third-party/supplier security review process
5. Limited incident response playbook coverage
6. Limited detection coverage outside email security
7. No formal incident notification decision workflow

## 90-Day Governance Improvement Roadmap

| Timeline | Priority | Action | Expected Outcome |
|---|---|---|---|
| Days 1-30 | Identity | Create Conditional Access and privileged access review checklist | Stronger access control governance |
| Days 1-30 | Incident Response | Finalize phishing incident workflow | Faster and more consistent response |
| Days 31-60 | Detection | Add identity and endpoint detections | Broader monitoring coverage |
| Days 31-60 | Vulnerability Management | Create vulnerability remediation workflow | Better patch governance |
| Days 61-90 | SaaS / Cloud | Create OAuth app and SaaS review checklist | Reduced third-party and cloud app risk |
| Days 61-90 | Reporting | Create incident notification decision workflow | Better regulatory and management readiness |

## Example: Phishing Incident Governance Mapping

| Incident Phase | Governance Question | Evidence |
|---|---|---|
| Detection | Was the malicious click detected quickly? | KQL detection and Sentinel rule |
| Triage | Was the incident reviewed by the SOC? | Playbook triage section |
| Investigation | Were email, identity, mailbox, and endpoint checks performed? | Playbook investigation steps |
| Containment | Were sessions revoked, passwords reset, or URLs blocked if needed? | Containment actions |
| Recovery | Was the account and endpoint returned to a safe state? | Recovery checklist |
| Reporting | Was management informed of risk and business impact? | Executive incident report |
| Improvement | Were controls improved after the incident? | SOC KPI dashboard and roadmap |

## Management Questions

Executives should be able to ask:

1. What are our most important cyber risks?
2. Which assets are covered by security monitoring?
3. Which controls are missing or inconsistent?
4. Are incidents handled consistently?
5. Are high-risk users, endpoints, and mailboxes protected?
6. Are we able to produce evidence after an incident?
7. Are we improving month over month?
8. Which security investments should be prioritized next?

## Disclaimer

This document is a portfolio-level governance mapping. It is not legal advice and does not determine whether a real organization is fully compliant with NIS2 or Finnish cybersecurity law.
