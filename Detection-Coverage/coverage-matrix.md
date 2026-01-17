# Detection Coverage Matrix

|  ATT&CK Tactic   |  Technique                |  Detection                             |
|------------------|---------------------------|----------------------------------------|
|  Initial Access  |  T1110 Brute Force        |  brute-force.spl                       |
|  Execution       |  T1059 PowerShell         |  suspicious-powershell.spl             |
|  Persistence     |  T1547 Registry Run Keys  |  registry-run-key-persistence.spl      |
|  Priv Esc        |  T1068 Exploitation       |  high-privilege-process-execution.spl  |
|  C2              |  T1071 DNS                |  dns-anomaly.spl                       |
