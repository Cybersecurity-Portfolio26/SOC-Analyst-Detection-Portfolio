# Threat Hunt: Privileged Escalation Detection

## Objective
Identify attempts to escalate privileges on compromised systems.

---

## Hypothesis
Attackers may attempt privilege escalation through token abuse, misconfigured services, or exploitation of vulnerabilities.

---

## Data Sources
- Windows Security Logs
- Process Creation Logs
- User Group Membership Logs

---

## Detection Logic

### New Admin Group Membership
'''spl
index=windows EventCode=4728 | stats count by user, group_name, actor
