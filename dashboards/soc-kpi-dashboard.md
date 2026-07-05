# SOC KPI Dashboard

## Purpose

This dashboard defines key security operations metrics for monitoring incident response performance, detection quality, and security program maturity.

The goal is to help management understand whether the security operations function is improving over time.

## Core SOC Metrics

| KPI | Description | Example Target |
|---|---|---|
| Mean Time to Detect | Average time between suspicious activity and alert creation | Under 30 minutes |
| Mean Time to Triage | Average time between alert creation and analyst review | Under 1 hour |
| Mean Time to Contain | Average time between confirmed incident and containment action | Under 4 hours |
| Mean Time to Recover | Average time between incident containment and return to normal operations | Under 24 hours |
| False Positive Rate | Percentage of alerts closed as benign | Below 30% |
| Incident Escalation Rate | Percentage of incidents escalated to senior security staff | Tracked monthly |
| Repeat Incident Rate | Number of repeated incidents from the same root cause | Decreasing trend |
| User Reporting Rate | Number of phishing emails reported by users | Increasing trend |
| Control Gap Closure Rate | Percentage of identified security gaps remediated | Increasing trend |

## Phishing Scenario Metrics

| Metric | Sample Value | Interpretation |
|---|---:|---|
| Suspicious emails delivered | 3 | Number of risky emails that reached users |
| Users who clicked | 3 | Users interacted with suspicious or benign links |
| Allowed malicious clicks | 2 | High-priority investigation required |
| Blocked malicious clicks | 1 | Control worked as expected |
| Confirmed compromised accounts | 0 | No compromise confirmed in sample data |
| Malicious URLs blocked | 2 | Email/web protection improvement opportunity |
| Users requiring password reset | 2 | Based on allowed malicious clicks |
| Mailboxes requiring rule review | 2 | Check for attacker persistence |

## Detection Quality Metrics

| Metric | Purpose |
|---|---|
| True Positive | Detection correctly identified malicious or suspicious activity |
| False Positive | Detection fired on benign activity |
| False Negative | Malicious activity occurred but was not detected |
| Detection Coverage | Percentage of important threat scenarios covered by rules |
| Detection Freshness | How recently detection logic was reviewed |
| Data Source Health | Whether required logs are available and complete |

## Operational Dashboard Example

| Security Area | Open Incidents | High Severity | Average Triage Time | Key Concern |
|---|---:|---:|---:|---|
| Identity | 4 | 1 | 45 minutes | Risky sign-ins |
| Email | 7 | 3 | 35 minutes | Phishing clicks |
| Endpoint | 5 | 2 | 1 hour | Suspicious PowerShell |
| Cloud/SaaS | 2 | 1 | 2 hours | Risky OAuth apps |
| Collaboration | 1 | 0 | 1 hour | External sharing |

## Management View

Security leadership should review:

1. Are high-severity incidents decreasing?
2. Are analysts responding faster?
3. Are the same incident types repeating?
4. Are important logs missing?
5. Are detection rules producing too many false positives?
6. Are control gaps being closed?
7. Are users reporting suspicious emails?
8. Are incident response playbooks being followed?

## Recommended Monthly SOC Review

Each month, the security team should review:

| Review Area | Question |
|---|---|
| Incident Trends | Which incident types increased or decreased? |
| Detection Performance | Which rules produced useful alerts? |
| False Positives | Which detections need tuning? |
| Response Speed | Did containment happen quickly enough? |
| Control Gaps | Which unresolved gaps create the most risk? |
| Governance | Are incident records complete enough for audit or regulatory review? |
| Roadmap | Which improvements should be prioritized next month? |

## Related Project Files

- `dashboards/executive-incident-report.md`
- `governance/security-control-inventory.md`
- `playbooks/phishing-user-clicked-url.md`
- `detections/email/malicious-url-clicked.kql`
- `sentinel-rules/malicious-url-clicked.yaml`
