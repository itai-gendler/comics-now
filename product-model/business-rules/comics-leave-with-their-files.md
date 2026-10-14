---
appliesTo:
- type: entity
  id: comic
  effect: removes
permits:
- actors:
  - admin
- unattended: true
references:
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
- kind: code
  role: implementation
  target: server/routes/admin/settings.js
---

# A comic leaves only when its file is gone or its library is removed

A scan removes a comic only when its file no longer exists; removing a library removes its comics with it.
