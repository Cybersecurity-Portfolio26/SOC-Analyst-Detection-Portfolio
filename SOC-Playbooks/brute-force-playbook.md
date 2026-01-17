# SOC Playbook: Brute Force Authentication Attack

## Purpose
Provide a standardized procedure for the detecting, investigating, and responding to brute force and password spraying attacks targeting authentication systems.

---

## Alert Triggers
- Excessive failed login attempts from a single IP
- Multiple failed logins across many users (password spraying)
- Successful login following repeated failures
- Authentication attempts outside normal business hours

---

## Initial Triage
1. Confirm alert source (SIEM, authentication logs)
2. Identify affected accounts and source IP(s)
3. Determine attack type:
   - Brute force (single user)
   - Password spraying (multiple users)
4. Check for successful authentication events

---

## Investigation Steps
- Review failed login events (Event ID 4625)
- Correlate successful logins (Event ID 4624)
- Analyze logon type (interactive, network, remote)
- Identify geographic anomalies (impossible travel)
- Review prior alerts involving the source IP

---

## Example Splunk Queries

### Failed Login Threshold
'''spl
index=windows EventCode=4625 | stats count by user, src_ip | where count > 10

---

## Severity Levels
- Low: Single user, no compromise
- Medium: Multiple users targeted
- High: Confirmed credential compromise or malware execution

---

## Escalation
Escalate to Tier-2 if:
- Malware persists after containment
- Priveleged account impacted
- Evidence of lateral movement
