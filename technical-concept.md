# Detection Concepts: Detection Logic, Detection Rule, Analytic Rule, Alert, Incident, and Playbook

This document is intended to clear up common confusion around the following concepts:

- Detection Logic
- Detection Rule
- Analytic Rule
- Alert
- Incident
- Playbook

## High-Level Flow

```text
Data → Detection → Alert → Incident → Response
         ↑                      ↓
    Detection Logic        Playbook
```

---

## Detection Logic

A **Detection Logic** is a generic concept.

It simply refers to the conditions used to decide whether an activity is suspicious.

### Examples

- 10 failed logins followed by a successful login
- PowerShell spawning `cmd.exe`
- User downloads malware
- Impossible travel sign-in

### Key Point

Detection logic is **not product-specific**. It applies to virtually all cybersecurity detection products and platforms.

---

## Detection Rule

A **Detection Rule** is the actual implementation of detection logic.

### Example

```text
If:
    10 failed logins are followed by a successful login

Then:
    Generate an alert
```

### In Microsoft

Detection rules are often built into the Defender suite and are typically managed by Microsoft.

Examples include:

- Malware detection
- Credential theft detection
- Suspicious PowerShell activity
- Identity-based attack detection

---

## Analytic Rule

An **Analytic Rule** is Microsoft Sentinel's version of a detection rule.

### Typical Flow

```text
Logs in Log Analytics
          ↓
    Analytic Rule
          ↓
         Alert
          ↓
       Incident
```

### Where It Lives

- Microsoft Sentinel ✅
- Microsoft Defender ❌

### Key Point

Analytic Rules are detections that SOC engineers can create, customize, and tune using KQL (Kusto Query Language).

---

## Alert

An **Alert** is the output of a detection.

An alert indicates that suspicious or malicious activity has been identified.

### Alert Sources

Alerts can come from:

- Defender for Endpoint
- Defender for Identity
- Defender for Cloud Apps
- Defender for Office 365
- Sentinel Analytic Rules

---

## Incident

An **Incident** is a collection of related alerts grouped together for investigation.

### Example

```text
Alert 1: Malware detected
Alert 2: Suspicious PowerShell
Alert 3: Credential dumping
```

These alerts may be grouped into a single incident:

```text
Incident:
Potential Endpoint Compromise
```

### Where It Lives

Incidents can exist in:

- Microsoft Defender
- Microsoft Sentinel

---

## Playbook

A **Playbook** is an automated response workflow.

In Microsoft environments, a Playbook is essentially an **Azure Logic App connected to Sentinel**.

### Example Flow

```text
Alert Created
      ↓
Playbook Runs
      ↓
Send Teams Message
      ↓
Create ServiceNow Ticket
      ↓
Disable User
      ↓
Isolate Device
```

### Common Use Cases

- Send notifications
- Create ITSM tickets
- Disable compromised accounts
- Isolate devices
- Trigger approval workflows

---

# Defender vs Sentinel

## Real-World Analogy

### Microsoft Defender

Think of Defender as the **Security Guards**.

Each Defender product focuses on protecting a specific area:

- Endpoints
- Identities
- Email
- Cloud Apps

Defender's primary role is:

- Detect threats
- Protect assets
- Investigate activity
- Perform automated remediation

### Microsoft Sentinel

Think of Sentinel as the **Security Operations Center (SOC)**.

Sentinel's primary role is:

- Collect data from multiple systems
- Correlate events
- Create custom detections
- Automate responses
- Provide centralized monitoring

---

## Use Defender For

- Endpoint protection
- Email protection
- Identity protection
- Threat detection
- Automated remediation
- Device investigation

---

## Use Sentinel For

- Central SOC monitoring
- Custom detections
- Cross-product correlation
- Compliance reporting
- Log retention
- SOAR automation
- Third-party integrations

---

# Quick Summary

| Concept | Purpose | Typically Lives In |
|----------|-----------|-------------------|
| Detection Logic | Idea/conditions that identify suspicious activity | Any security platform |
| Detection Rule | Implementation of detection logic | Defender, SIEMs, security tools |
| Analytic Rule | Sentinel detection rule | Sentinel |
| Alert | Output of a detection | Defender, Sentinel |
| Incident | Group of related alerts | Defender, Sentinel |
| Playbook | Automated response workflow | Sentinel (Azure Logic Apps) |

## Rule of Thumb

**Defender = Detect & Protect**

**Sentinel = Correlate & Orchestrate**
