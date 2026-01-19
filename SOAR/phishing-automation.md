# Phishing Response Automation (SOAR)

## Purpose
This document outlines a SOAR workflow for detecting, enriching, and responding to
suspected phishing emails.

The automation is designed to **reduce response time**, **improve consistency**, and
**assist Tier-1 analysts**, while ensuring all impactful actions remain subject to
human review.

---

## Use Case
Suspicious or malicious emails reported by users or detected by email security controls.

---

## Trigger Conditions
Automation is triggered when **any** of the following occur:

- User-reported phishing email
- Email flagged by secure email gateway (SEG)
- Email containing suspicious URLs or attachments
- Multiple users receiving similar suspicious emails

---

## Data Inputs
- Email headers and metadata
- Email body and attachment hashes
- Embedded URLs
- Sender domain reputation
- Threat intelligence feeds

---

## Automated Actions

### 1. Email Parsing & Enrichment
SOAR automatically extracts:
- Sender address and domain
- SPF, DKIM, DMARC results
- URLs and attachments
- Message IDs and timestamps

---

### 2. Reputation & Threat Intelligence Checks
Automation performs:
- URL reputation lookups
- Attachment hash lookups (VirusTotal or equivalent)
- Sender domain age and reputation analysis

---

### 3. Scope Identification
SOAR searches email logs to determine:
- Number of recipients
- Whether the email was delivered, blocked, or clicked
- If multiple users received identical messages

---

### 4. Risk Scoring
Automation assigns a risk score based on:
- Known malicious indicators
- Credential harvesting patterns
- Impersonation indicators
- User interaction (clicks or downloads)

---

### 5. Ticket Creation
SOAR generates a SOC ticket including:
- Risk score and verdict
- Affected users
- Indicators of compromise (IOCs)
- Timeline of events
- Recommended analyst actions

---

## Analyst Review (Human-in-the-Loop)

Tier-1 analyst validates:
- Email legitimacy
- Threat intelligence results
- User interaction impact

### Analyst Decisions
- Close as false positive
- Classify as suspicious and monitor
- Escalate to Tier-2 for containment

---

## Optional Tier-2 Response Actions
If escalated, Tier-2 may:
- Quarantine or delete emails from mailboxes
- Block sender domain or URLs
- Reset affected user credentials
- Notify impacted users

---

## Safety Controls
- Automation does not delete emails automatically
- Internal and trusted domains are excluded
- Known phishing simulations are ignored
- All remediation actions require approval

---

## MITRE ATT&CK Mapping
- T1566 – Phishing
- T1566.001 – Spearphishing Attachment
- T1566.002 – Spearphishing Link

---

## Example Automated Summary
> Suspicious email reported by multiple users.
> Embedded URL flagged as malicious.
> Two users clicked the link.
> Alert enriched and escalated for Tier-2 containment.

---

## Notes
This SOAR workflow focuses on **assistive automation** to support SOC analysts
by speeding investigation while preserving human decision-making authority.
