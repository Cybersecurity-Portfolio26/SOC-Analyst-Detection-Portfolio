# Phishing Alert Triage Guide

## Purpose
This document outlines the Tier-1 SOC workflow for validating and triaging phishing alerts,
assessing user impact, and determining escalation.

Tier-1 analysts are responsible for **validation, investigation, documentation, and escalation** —
not mailbox remediation or user communication unless directed.

---

## Alert Sources
Phishing alerts may originate from:
- Email Security Gateways
- User-reported phishing (phish button)
- SIEM correlation rules
- Endpoint alerts triggered by email attachments or links

---

## Step 1: Alert Validation
Confirm the alert represents a real and current phishing event.

### Validation Checks
- Alert timestamp is recent
- Email exists in the mail system
- Sender and recipient information is available
- Alert is not a simulated phishing test

**Outcome**
- Invalid / test email → Close
- Valid alert → Continue triage

---

## Step 2: Email Context Gathering
Collect key details about the email.

### Required Information
- Sender email address and domain
- Recipient(s)
- Subject line
- Attachment name or URL (if present)
- Delivery and interaction status (opened, clicked)

---

## Step 3: Sender and Domain Analysis
Assess sender legitimacy.

### Review:
- Sender domain reputation
- Domain age
- SPF/DKIM/DMARC results
- Signs of impersonation or lookalike domains

**Indicators of Concern**
- Recently registered domains
- SPF/DKIM failures
- Display name spoofing

---

## Step 4: Content Analysis
Analyze email content for phishing indicators.

### Indicators to Review
- Urgent or threatening language
- Requests for credential submission
- Unexpected attachments or links
- HTML attachments

**Common Phishing Types**
- Credential harvesting
- Malware delivery
- Business email compromise (BEC)

---

## Step 5: Attachment and URL Review
Determine the risk of payloads or links.

### Actions
- Identify attachment type (HTML, ZIP, ISO, DOCM)
- Review URLs for shortening, obfuscation, or mismatches
- Check reputation using threat intelligence sources

**Indicators of Concern**
- HTML attachments prompting login
- Office documents with macros
- URLs redirecting through multiple domains

---

## Step 6: User Interaction Assessment
Determine impact.

### Questions
- Did any users open the attachment?
- Did any users click the link?
- Were credentials submitted?

**Risk Consideration**
- User interaction significantly increases severity

---

## Step 7: Scope Assessment
Determine if the phishing email was widespread.

### Scope Checks
- Number of recipients
- Additional reports from users
- Similar emails observed in logs

---

## Step 8: Decision Matrix

| Finding | Action |
|------|------|
| Benign or legitimate email | Close |
| Suspicious email, no interaction | Monitor / Document |
| Confirmed phishing with interaction | Escalate |

---

## Step 9: Escalation Criteria
Escalate to Tier-2 if any of the following are present:
- Credential harvesting attempts
- Malware attachment
- Multiple recipients affected
- Confirmed user interaction
- Privileged users targeted

---

## Documentation Requirements
Each alert must include:
- Email summary
- Indicators observed
- Impact assessment
- Decision rationale
- Analyst notes and timestamps

---

## MITRE ATT&CK Mapping
Common phishing techniques:
- T1566.001 – Phishing: Attachment
- T1566.002 – Phishing: Link

---

## Example Triage Summary
> Phishing email detected from external sender targeting multiple users. 
> HTML attachment observed prompting credential submission. 
> Two users opened the attachment. 
> Alert escalated to Tier-2 for response and containment.

---

## Tier-1 Analyst Notes
- Do not delete emails or reset credentials unless directed
- Focus on accurate analysis and impact determination
- Escalate promptly when user interaction is confirmed
