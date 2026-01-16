# Detection Engineering Overview

## Detection Philosophy
Detections are designed to prioritize high-signal activity while minimizing false positives through thresholding and contextual enrichment.

## Design Principles
- Use behavior-based detection over static indicators
- Map detections to MITRE ATT&CK
- Tune thresholds based on environment baselines

## Example
Brute-force detection tuned to trigger only after repeated failures from the same source within a defined time window.
