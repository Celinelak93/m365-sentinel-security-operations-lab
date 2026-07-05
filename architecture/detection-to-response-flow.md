# Detection to Response Flow

## Purpose

This document explains how a suspicious event becomes a security incident and how the security team responds.

## Flow

```text
Security Event
  ↓
Detection Logic
  ↓
Analytics Rule
  ↓
Alert
  ↓
Incident
  ↓
Triage
  ↓
Investigation
  ↓
Containment
  ↓
Remediation
  ↓
Reporting
  ↓
Control Improvement


Example

A user clicks a malicious URL in an email.

The detection checks URL click activity, email delivery, user identity activity, endpoint behavior, and mailbox changes.

The analyst then determines whether the user account, mailbox, or endpoint was compromised.

Response Actions

Possible response actions include:

Block URL or sender domain
Reset user password
Revoke active sessions
Review mailbox forwarding and inbox rules
Investigate endpoint activity
Isolate device if compromise is suspected
Document the incident
Update detection logic or controls
