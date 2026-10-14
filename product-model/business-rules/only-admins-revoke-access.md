---
appliesTo:
- type: entity
  id: access-grant
  effect: removes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/admin/users.js
---

# Only admins revoke access

Only admins close a library, publisher, series, folder or comic to a user.
