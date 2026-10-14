---
appliesTo:
- type: entity
  id: library
  effect: creates
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/admin/settings.js
---

# Only admins add libraries

Which folders on the server are libraries is an admin's decision.
