# Threat Hunt: Persistence Mechanisms

## Objective
Detect techniques used by attackers to maintain long-term access to compromised systems.

---

## Hypothesis
Attackers often establish persistence via scheduled tasks, registry run keys, or startup scripts to survive reboots.

---

## Data Sources
- Windows Security Logs
- Registry Modification Logs
- Scheduled Task Events

---

## Detection Logic

### Scheduled Task Creation
'''spl
index=windows EventCode=4698 | stats count by Task_Name, Author
