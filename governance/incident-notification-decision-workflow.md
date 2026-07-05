# Incident Notification Decision Workflow

## Purpose

This document provides a simple decision workflow for determining whether a cybersecurity incident should be escalated for management, legal, regulatory, or customer notification review.

This is a governance workflow, not legal advice.

## Decision Flow

```text
Security Incident Detected
  ↓
Is the incident confirmed or still under investigation?
  ↓
Does it affect critical services, sensitive data, identity systems, production systems, or many users?
  ↓
Is there evidence of account compromise, malware execution, data access, data loss, or service disruption?
  ↓
Could the incident have significant operational, financial, legal, or customer impact?
  ↓
Escalate to Security Leadership / Legal / Compliance for notification decision

Notification Review Questions
Question	Why It Matters
What happened?	Defines the incident type
When did it start?	Supports timeline and reporting obligations
When was it detected?	Measures detection capability
Which systems or users were affected?	Defines scope
Was service disrupted?	Determines operational impact
Was data accessed or lost?	Determines confidentiality impact
Was malware executed?	Determines technical severity
Was identity compromise confirmed?	Determines account risk
Were customers affected?	Determines external communication need
Has the incident been contained?	Determines current risk
Is there cross-border impact?	Determines broader reporting concern
What evidence supports the conclusion?	Supports auditability
Severity Escalation Guide
Severity	Example Condition	Escalation
Low	Suspicious event blocked, no compromise	SOC review only
Medium	User clicked malicious link, no confirmed compromise	SOC lead review
High	Credentials entered or suspicious sign-in observed	Security leadership review
Critical	Confirmed compromise, data access, malware, or service disruption	Security, legal, compliance, and executive review
Example: Malicious URL Click
Finding	Notification Relevance
User clicked a malicious URL but click was blocked	Usually low notification concern
User clicked and entered credentials	Escalate for identity compromise review
Suspicious sign-in occurred after click	Escalate for account compromise review
Mailbox forwarding rule was created	Escalate for data exposure review
Malware executed on endpoint	Escalate for endpoint compromise review
Multiple users affected across business units	Escalate for broader incident review
Evidence Checklist

Before escalation, collect:

Incident timeline
Affected users
Affected systems
Detection source
Email/message evidence
URL/domain evidence
Sign-in activity
Mailbox activity
Endpoint activity
Containment actions
Remaining risk
Recommended next actions
Related Project Files
playbooks/phishing-user-clicked-url.md
dashboards/executive-incident-report.md
governance/nis2-readiness-mapping.md
governance/security-control-inventory.md
