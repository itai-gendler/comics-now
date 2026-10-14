---
appliesTo:
- type: entity
  id: tagging-scan
  effect: creates
permits:
- actors:
  - admin
- unattended: true
references:
- kind: code
  role: implementation
  target: server/routes/admin/comictagger.js
---

# Only admins and the tagging schedule start a tagging scan

Tagging scans are started by an admin or by the server when the tagging schedule elapses.
