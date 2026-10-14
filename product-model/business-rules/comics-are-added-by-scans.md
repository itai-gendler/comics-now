---
appliesTo:
- type: entity
  id: comic
  effect: creates
permits:
- actors:
  - admin
- unattended: true
references:
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
---

# Only scans add comics

Comics come into the catalogue only when a scan, started by an admin or by the server's interval, finds their files.
