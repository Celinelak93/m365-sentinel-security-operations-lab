# Incident Response Playbook: User Clicked Malicious URL

## Purpose

This playbook describes how a security operations team should investigate and respond when a user clicks a malicious URL from an email.

This scenario connects email security, identity security, endpoint security, mailbox investigation, containment, and management reporting.

## Incident Trigger

This playbook is triggered when one or more of the following occurs:

- Defender for Office 365 reports a malicious URL click
- Microsoft Sentinel creates an incident for suspicious URL activity
- A user reports clicking a suspicious link
- A phishing campaign is detected and at least one user interacted with the message

## Initial Triage Questions

The analyst should answer:

1. Who clicked the URL?
2. What email contained the URL?
3. Was the URL blocked or allowed?
4. Was the user redirected to a credential harvesting page?
5. Did the user enter credentials?
6. Did the user have suspicious sign-in activity after the click?
7. Was a suspicious inbox rule created?
8. Did the endpoint show suspicious process, file, or network activity?
9. Were other users targeted by the same campaign?

## Evidence to Collect

| Evidence | Source |
|---|---|
| Sender address | Defender for Office 365 |
| Recipient list | EmailEvents |
| URL clicked | UrlClickEvents |
| Click timestamp | UrlClickEvents |
| Delivery status | EmailEvents |
| User sign-in activity | Entra ID sign-in logs |
| Mailbox rules | Exchange audit logs |
| Endpoint process activity | Defender for Endpoint |
| Endpoint network connections | Defender for Endpoint |
| Related alerts | Defender XDR / Sentinel |

## Investigation Steps

### 1. Identify the affected user

Determine which user clicked the malicious link.

Questions:

- Was the click blocked?
- Was the click allowed?
- Did the user click more than once?
- Did other users click the same URL?

### 2. Investigate the email

Review the original email.

Questions:

- Who sent the email?
- Was the sender external?
- Was the sender spoofed?
- Was the message part of a larger campaign?
- Did the message contain attachments?
- Was the email delivered to inbox, junk, or quarantine?

### 3. Investigate identity activity

Review the user's sign-in activity after the click.

Look for:

- Unusual location
- Impossible travel
- Failed MFA attempts
- MFA fatigue patterns
- New device or browser
- Login from anonymizing proxy or VPN
- Privileged role activity

### 4. Investigate mailbox activity

Check whether the attacker created persistence or exfiltration mechanisms.

Look for:

- New inbox rules
- External forwarding
- Mailbox delegation changes
- Suspicious send activity
- Deleted security alerts
- Unusual mailbox access

### 5. Investigate endpoint activity

Check the user's device for suspicious behavior after the click.

Look for:

- Suspicious PowerShell
- Browser spawning command-line tools
- Downloaded executables
- Suspicious file creation
- Connections to suspicious domains
- Malware or EDR alerts

## Containment Actions

Based on severity, perform one or more of the following:

| Action | When to Use |
|---|---|
| Reset user password | User may have entered credentials |
| Revoke user sessions | Suspicious sign-in activity exists |
| Require MFA re-registration | MFA compromise is suspected |
| Block sender/domain | Campaign is ongoing |
| Block URL/domain | URL is confirmed malicious |
| Purge email | Email was delivered to multiple users |
| Remove inbox rules | Suspicious mailbox rule found |
| Isolate endpoint | Endpoint compromise is suspected |
| Disable account temporarily | Active compromise is likely |

## Eradication and Recovery

After containment:

1. Remove malicious emails from user mailboxes.
2. Remove suspicious inbox rules or forwarding.
3. Confirm the user has reset credentials.
4. Confirm active sessions were revoked.
5. Confirm endpoint is clean.
6. Restore normal account access if safe.
7. Educate affected user.
8. Update detection logic if needed.

## Severity Guidance

| Severity | Condition |
|---|---|
| Low | User clicked but URL was blocked, no suspicious activity found |
| Medium | User clicked allowed URL, but no confirmed compromise |
| High | User entered credentials or suspicious sign-in activity occurred |
| Critical | Account compromise, data access, endpoint compromise, or lateral movement confirmed |

## Communication

### User Communication

Inform the user:

- The link was suspicious or malicious
- Their account may require password reset
- They should report similar emails immediately
- They should not delete the original email until investigation is complete

### Management Communication

Provide a short summary:

- Number of users targeted
- Number of users who clicked
- Whether compromise was confirmed
- Actions taken
- Remaining risk
- Recommended improvements

## Post-Incident Review

After the incident, review:

1. Did Safe Links block the URL?
2. Did the alert fire quickly enough?
3. Were all targeted users identified?
4. Was the response process clear?
5. Were containment actions completed?
6. Should anti-phishing policies be tuned?
7. Should user awareness training be updated?
8. Should a new detection rule be created?

## Related Controls

| Control Area | Related Control |
|---|---|
| Email security | Safe Links, Safe Attachments, anti-phishing policies |
| Identity security | MFA, Conditional Access, risky sign-in detection |
| Endpoint security | Defender for Endpoint, attack surface reduction |
| Security operations | Sentinel incident triage, playbook execution |
| Governance | Incident documentation, management reporting |

## Related Project Files

- `detections/email/malicious-url-clicked.kql`
- `sentinel-rules/malicious-url-clicked.yaml`
- `dashboards/soc-kpi-dashboard.md`
- `governance/security-control-inventory.md`
