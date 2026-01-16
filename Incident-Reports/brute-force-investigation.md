# Brute Force Authentication Attack

## Detection Source
SIEM - Windows Security Logs

## Severity
Medium

## MITRE ATT&CK
- T1110 - Brute Force

## Summary
Multiple failed authentication attempts were detected against a Windows host from a single external IP address within a short time window.

## Investigation
- Identified a high volume of Event ID 4625 (failed logons)
- Correlated source IP across multiple usernames
- Verified no successful authentication occurred
- Confirmed the activity was external and automated

## Indicators of Compromise
- Source IP: 185.xxx.xxx.xxx
- Target Host: WIN-01
- Event ID: 4625

## Response Actions
- Recommended blocking the source IP
- Suggested enforcing account lockout policy
- Recommneded MFA for privileged accounts

## Outcome
No compromise confirmed. Activity mitigated.
