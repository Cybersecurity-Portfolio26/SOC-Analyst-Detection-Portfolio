# Brute Force Alert Triage Guide

## Alert Description
Multiple failed authentication attempts from a single source IP.

## Initial Triage Steps
1. Validate alert accuracy
2. Identify target accounts
3. Check for successful logins after failures
4. Assess source IP reputation

## Decision Tree
- Internal IP --> Investigate lateral movement
- External IP --> Possible credential stuffing
- Success after failures --> Escalate severity

## Escalation Criteria
- Priveleged account targeted
- Successful authentication observed
- Multiple hosts affected
