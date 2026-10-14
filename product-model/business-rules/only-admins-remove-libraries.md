---
appliesTo:
- type: entity
  id: library
  effect: removes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/admin/settings.js
---

# Only admins remove libraries

Removing a library takes its comics out of everyone's view, so only admins do it.
