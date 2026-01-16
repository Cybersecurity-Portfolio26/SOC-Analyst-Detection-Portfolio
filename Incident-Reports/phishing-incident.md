# Phishing Email Investigation

## Detection Source
Email Security Gateway / User Report

## Severity
Medium

## MITRE ATT&CK
- T1566.001 - Phishing: Spearphishing Link

## Summary
A phishing email impersonating a trusted vendor was reported by a user.

## Investigation
- Analyzed email headers and sender domain
- Inspected embedded URL and confirmed malicious redirect
- Checked proxy and authentication logs for user interaction

## Indicators of Compromise
- Malicious URL: hxxp://login-secure[.]example
- Sender domain: spoofed-vendor[.]com

## Response Actions
- Blocked sender domain and URL
- Reset credentials for potentially impacted users
- Notified users via security awareness message

## Outcome
No credential compromise detected.
