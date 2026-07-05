# Executive Incident Report: Malicious URL Click

## Incident Summary

A phishing email was delivered to multiple users. At least one user clicked a suspicious or malicious URL. The security team investigated email delivery, URL click activity, identity activity, mailbox changes, and endpoint behavior to determine whether compromise occurred.

## Executive Overview

| Field | Details |
|---|---|
| Incident Type | Phishing / Malicious URL Click |
| Severity | High |
| Status | Contained |
| Primary Risk | Credential theft and account compromise |
| Affected Users | 3 suspicious recipients identified |
| Confirmed Clicks | 2 allowed suspicious clicks |
| Confirmed Compromise | Not confirmed in this sample scenario |
| Business Impact | Limited, pending further investigation |
| Response Owner | Security Operations Team |

## Timeline

| Time | Event |
|---|---|
| 08:10 UTC | Phishing email delivered to user mailbox |
| 08:14 UTC | User clicked suspicious Microsoft 365 credential-themed URL |
| 08:16 UTC | Another user clicked a phishing URL that was blocked |
| 08:21 UTC | User clicked malware-related file-sharing URL |
| 09:00 UTC | Security team reviewed URL click and email delivery evidence |
| 09:20 UTC | Containment actions recommended |

## Key Findings

1. A phishing email impersonating Microsoft 365 security notifications was delivered to a user inbox.
2. One user clicked a phishing URL and the click was allowed.
3. One user clicked a phishing URL that was blocked.
4. One user clicked a malware-related file-sharing URL.
5. A benign newsletter click was also observed and should not be treated as malicious.
6. No confirmed account compromise is included in the synthetic dataset.
7. Further identity and endpoint investigation would be required in a real incident.

## Affected Users

| User | Event | Severity | Reason |
|---|---|---|---|
| anna.korhonen@contoso.com | Clicked phishing URL | High | Click was allowed and URL was classified as phishing |
| mikko.lahti@contoso.com | Clicked phishing URL | Medium | URL was classified as phishing but click was blocked |
| elina.saarinen@contoso.com | Clicked malware-related URL | High | Click was allowed and URL was classified as malware |
| joonas.virtanen@contoso.com | Clicked newsletter URL | Low | No threat classification |

## Business Risk Assessment

| Risk Area | Assessment |
|---|---|
| Credential Theft | Possible if user entered credentials after clicking |
| Account Compromise | Not confirmed, but should be investigated |
| Mailbox Persistence | Unknown; mailbox rules and forwarding should be reviewed |
| Endpoint Compromise | Unknown; endpoint activity should be reviewed |
| Data Loss | Not confirmed |
| Lateral Movement | Not confirmed |
| Regulatory Reporting | Not required unless compromise or significant impact is confirmed |

## Recommended Containment Actions

| Action | Priority | Owner |
|---|---|---|
| Reset password for users with allowed malicious clicks | High | Identity / IT |
| Revoke active sessions for affected users | High | Identity / IT |
| Review sign-in logs after click timestamps | High | Security Operations |
| Review mailbox rules and forwarding | High | Messaging / Security |
| Investigate endpoint activity for affected devices | Medium | Endpoint Security |
| Block malicious URLs and sender domains | High | Email Security |
| Search for additional recipients | High | Security Operations |
| Document incident evidence | Medium | Security Operations |

## Management Summary

The incident demonstrates a realistic phishing risk where users may click malicious links delivered through email. Although confirmed compromise is not shown in this sample scenario, allowed malicious clicks create a serious risk of credential theft, mailbox compromise, and follow-on attacker activity.

The security team should prioritize identity investigation, mailbox review, endpoint validation, and improvements to email protection policies.

## Control Improvement Recommendations

| Control Area | Improvement |
|---|---|
| Email Security | Tune Safe Links and anti-phishing policies |
| Identity Security | Enforce Conditional Access and session revocation procedures |
| Endpoint Security | Review device activity after malicious clicks |
| Security Operations | Build detection rules for malicious URL clicks |
| User Awareness | Train users to report suspicious Microsoft 365 login prompts |
| Governance | Include phishing response in incident reporting workflow |

## Related Project Files

- `playbooks/phishing-user-clicked-url.md`
- `detections/email/malicious-url-clicked.kql`
- `sentinel-rules/malicious-url-clicked.yaml`
- `sample-data/synthetic-url-click-events.csv`
- `sample-data/synthetic-email-events.csv`
- `governance/security-control-inventory.md`
