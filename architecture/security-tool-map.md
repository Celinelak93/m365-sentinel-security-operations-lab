

This document maps each security area to the Microsoft tools used for prevention, detection, investigation, and response.

| Security Area | Prevention | Detection | Investigation | Response |
|---|---|---|---|---|
| Identity | Conditional Access, MFA, PIM | Entra ID risk detections, Sentinel analytics | Sign-in logs, audit logs, user risk events | Revoke sessions, reset password, disable account |
| Endpoint | Defender for Endpoint, Intune, ASR rules | Defender alerts, process events, file events | Device timeline, process tree, network connections | Isolate device, collect investigation package, quarantine file |
| Email | Safe Links, Safe Attachments, anti-phishing policies | EmailEvents, UrlClickEvents, Defender alerts | Email headers, delivery status, click activity | Block sender/domain, purge email, quarantine message |
| Collaboration | SharePoint/OneDrive sharing controls, DLP | File activity alerts, external sharing events | Audit logs, sharing links, user activity | Remove sharing links, revoke access, quarantine file |
| Cloud/SaaS | App governance, OAuth app controls | Cloud app alerts, OAuth consent events | App activity logs, user activity, app permissions | Revoke app consent, block app, enforce session control |
| SOC | Analytics rules, automation rules | Sentinel incidents, Defender XDR incidents | Incident timeline, entities, hunting queries | Playbooks, escalation, containment, reporting |
