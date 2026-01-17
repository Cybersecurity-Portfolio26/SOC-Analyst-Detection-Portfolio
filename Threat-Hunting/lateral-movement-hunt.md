# Threat Hunt: Lateral Movement Detection

## Objective
Identify potential lateral movement activity within the enterprise network following initial host compromise.

---

## Hypothesis
An attacker with valid credentials may attempt to move laterally using remote services such as SMB, RDP, or Windows Remote Management.

---

## Data Sources
- Windows Security Logs
- Network Authentication Logs
- Endpoint Process Creation Logs

---

## Detection Logic

### Network Logons Across Multiple Hosts
'''spl
index=windows EventCode=4624 Logon_Type=3 | stats count by user, src_ip, dest_host | where count > 5
