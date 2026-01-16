# Threat Hunt: Lateral Movement Detection

## Analysis
Detected multiple successful network logons from a single source host to multiple destinations within a short time window.

## Objective
Identify signs of lateral movement within the internal network.

## Data Sources
- Windows Security Logs
- Network Authentication Logs

## Hypothesis
If an attacker compromises a host, they may attempt to move laterally using remote services or credential reuse.

## Splunk Query
'''spl
index=windows EventCode=4624 Logon_Type=3 | stats count by user, src_ip, dest_host | where count > 5

## Conclusion
Activity reviewed and flagged for further investigation.
