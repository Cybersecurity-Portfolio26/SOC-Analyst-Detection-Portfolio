# Suspicious DNS Tunneling Activity

## Detection Source
DNS Logs

## Severity
High

## MITRE ATT&CK
- T1071.004 - DNS

## Summary
Unusual DNS query volume and length suggested potential command-and-control activity.

## Investigation
- Identified high-frequency DNS requests
- Detected long, randomized subdomain strings
- Correlated activity to a single internal host

## Indicators of Compromise
- Excessive DNS queries
- Host: DEV-PC-11

## Response Actions
- Recommended DNS sinkholing
- Isolated host for forensic analysis

## Outcome
Potential C2 activity disrupted.
