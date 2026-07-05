# Synthetic Sample Data

## Purpose

This folder contains synthetic sample data used to demonstrate the detection logic in this security operations lab.

The data is fictional and does not represent real users, real organizations, or real security incidents.

## Files

| File | Purpose |
|---|---|
| `synthetic-url-click-events.csv` | Simulates URL click activity from email messages |
| `synthetic-email-events.csv` | Simulates email delivery and threat classification events |

## Scenario Represented

The main scenario is:

A user receives a phishing email and clicks a malicious URL. The security team must investigate whether the user, mailbox, identity, or endpoint was compromised.

## Example Suspicious Events

| User | Scenario | Expected Severity |
|---|---|---|
| `anna.korhonen@contoso.com` | Clicked a phishing URL that was allowed | High |
| `mikko.lahti@contoso.com` | Clicked a phishing URL that was blocked | Low or Medium |
| `elina.saarinen@contoso.com` | Clicked a malware-related URL that was allowed | High |
| `joonas.virtanen@contoso.com` | Clicked a normal newsletter URL | Low / benign |

## Important Note

These CSV files are for portfolio demonstration only.

They are not exported from a real Microsoft Defender XDR or Sentinel environment. They are designed to help readers understand what the detection query is looking for.
