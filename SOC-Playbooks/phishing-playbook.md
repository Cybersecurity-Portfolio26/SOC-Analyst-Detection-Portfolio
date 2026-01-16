# SOC Playbook: Phishing Incident Response

## Purpose
Define procedures for identifying, analyzing, and responding to phishing email incidents.

---

## Alert Triggers
- User-reported phishing email
- Email security gateway alert
- Suspicious links or attachments detected
- Credential harvesting indicators

---

## Initial Triage
1. Review email headers and sender reputation
2. Identify targeted users and distribution scope
3. Determine phishing type:
   - Credential harvesting
   - Malware delivery
   - Business Email Compromise (BEC)

---

## Investigation Steps
- Analyze email headers (SPF, DKIM, DMARC)
- Extract and analyze URLs or attachments
- Check URLs against threat intelligence
- Search for similar emails across environment
- Review authentication logs for compromised credentials

---

## Containment Actions
- Quarantine malicious emails
- Block sender domains and URLs
- Force password resets for affected users
- Revoke active sessions if credentials exposed

---

## Eradication
- Remove phishing emails from mailboxes
- Update email filtering rules
- Disable compromised accounts temporarily

---

## Recovery
- Restore user access after credential reset
- Monitor for suspicious login activity
- Validate no lateral movement occurred

---

## User Awareness
- Notify affected users
- Provide phishing awareness guidance
- Encourage future reporting of suspicious emails

---

## Post-Incident Actions
- Document indicators and response actions
- Tune phishing detection rules
- Update SOC knowledge base

---

## MITRE ATT&CK Mapping
- Initial Access: T1566 (Phishing)
- Credential Access: T1056 (Input Capture)
- Impact: T1499 (Endpoint Denial of Service - if malware delivered)
