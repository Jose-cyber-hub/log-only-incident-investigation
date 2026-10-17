# Log-Only Incident Investigation

> Bootcamp lab: simulated scenario (TripleTen Cybersecurity, 2026)

## Context
It started with a Friday 3 AM SIEM alert: a Tech Support user
connected to the HR database server over SMB from a plant engineer's 
workstation, running native binaries (hostname.exe, whoami.exe), with
no malware. I had no access to the machines, only logs: Sysmon and 
Windows Security events from several hosts. I had to rebuild the story 
from Event IDs alone and map it to MITRE ATT&CK.

## What I did
- Rebuilt the attack timeline from Sysmon and Windows Security
  Event IDs across several hosts.
- Mapped the activity to MITRE ATT&CK, including living-off-the-land
  tools (PsExec, WMIC), C2 beaconing on port 8080 from the backup
  server, and a process masquerading as OneDrive.exe.
- Tested the log-tampering hypothesis by searching for Event ID 1102
  (audit log cleared) across the whole index and found no evidence.
- Documented where telemetry was missing and treated those gaps
  as findings.
- Assessed the business risk, including data-protection
  implications under Colombia's Ley 1581 and GDPR.
- Proposed a 7-control remediation plan.


## Tools & methods
Sysmon, Windows Security Event Logs, MITRE ATT&CK, timeline
analysis, log correlation.

## Results
An attack narrative reconstructed from logs alone, mapped to
MITRE ATT&CK, with business impact and prioritized remediation.

## Deliverables
- Report: /proyecto sprint 3.pdf

## Instructor review
Approved. Praised for the multi-host Event-ID timeline and for
treating missing telemetry as a finding.

## What I learned
When logs are missing, that's a finding too, not a hole to hide.
I learned to keep an executive summary short enough for a busy
reader, to describe diagrams in text so they work for everyone,
and to show my correlation reasoning inside the timeline instead
of only listing events.
