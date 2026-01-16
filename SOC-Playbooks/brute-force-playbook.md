# SOC Playbook: Brute Force Attack

## Trigger
Multiple failed authentication attempts detected.

## Triage Steps
1. Validate alert severity
2. Review authentication logs
3. Identify source IP and target accounts

## Containment
- Block malicious IP
- Lock affected accounts if needed

## Eradication
- Reset compromised credentials
- Enforce MFA

## Lessons Learned
Review lockout thresholds and detection tuning.
