# Brute Force Response Automation (SOAR)

## Purpose
This document describes a Security Orchestration, Automation, and Response (SOAR)
workflow for responding to brute-force authentication attacks.

The goal of this automation is to **reduce analyst workload**, **speed containment**,
and **standardize response actions**, while keeping final decisions under analyst control.

---

## Use Case
High-volume authentication failures indicative of brute-force or password spray attacks.

---

## Trigger Conditions
Automation is triggered when **all** of the following conditions are met:

- Authentication failures exceed defined threshold
- Source IP is external
- Multiple user accounts targeted OR privileged account targeted
- Events occur within a short time window

### Example Threshold
- ≥50 failed logins
- Within 5 minutes
- From a single source IP

---

## Data Inputs
- Authentication logs (AD, VPN, Cloud IAM)
- User account metadata
- Source IP reputation
- Geo-location data

---

## Automated Actions

### 1. Alert Enrichment
The SOAR platform automatically:
- Identifies affected users
- Determines if accounts are privileged
- Checks source IP reputation
- Performs geo-IP lookup

---

### 2. Correlation Checks
Automation performs additional lookups:
- Checks for successful logins from same IP
- Checks for similar activity on other systems
- Identifies account spray patterns

---

### 3. Severity Adjustment
Based on enrichment results:
- Increase severity if admin/service accounts targeted
- Increase severity if successful login observed
- Maintain severity if failures only

---

### 4. Analyst Notification
Automation generates a SOC ticket containing:
- Summary of findings
- Affected accounts
- Evidence and timelines
- Recommended next steps

---

## Analyst Decision Point (Human-in-the-Loop)
Automation **does not** take disruptive actions automatically.

Tier-1 analyst reviews:
- Enriched alert details
- Authentication outcomes
- Risk indicators

### Analyst Decisions
- Close as false positive
- Monitor for additional activity
- Escalate to Tier-2

---

## Optional Tier-2 Actions (Not Automated by Default)
If escalated, Tier-2 may:
- Temporarily lock affected accounts
- Block source IP at firewall
- Initiate incident response procedures

---

## Failure and Safety Controls
To prevent unintended disruption:
- Automation excludes known internal IP ranges
- Automation ignores approved vulnerability scans
- Automation does not modify accounts without approval

---

## Benefits of Automation
- Faster alert triage
- Reduced analyst fatigue
- Consistent response
- Improved detection accuracy

---

## MITRE ATT&CK Mapping
- T1110 – Brute Force
- T1110.003 – Password Spraying

---

## Example Automated Summary
> High-volume authentication failures detected from external IP targeting multiple user accounts.
> No successful logins observed. Source IP flagged as high risk.
> Alert enriched and presented for analyst review.

---

## Notes
This SOAR workflow is designed to support Tier-1 SOC analysts by automating
data gathering and enrichment while preserving analyst judgment and escalation authority.
