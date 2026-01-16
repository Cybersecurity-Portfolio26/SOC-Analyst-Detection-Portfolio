# Suspicious PowerShell Activity

## Detection Source
Windows Process Creation Logs

## Severity
High

## MITRE ATT&CK
- T1059.001 - PowerShell

## Summary
Encoded PowerShell commands were detected executing on a workstation.

## Investigation
- Identified PowerShell with -EncodedCommand flag
- Correlated execution with outbound network traffic
- Determined activity was malicious

## Indicators of Compromise
- CommandLine contained Base64-encoded payload
- Host: FINANCE-PC-03

## Response Actions
- Isolated endpoint
- Disabled PowerShell for non-admin users
- Recommended enhanced logging (Script Blocked Logging)

## Outcome
Threat contained.
