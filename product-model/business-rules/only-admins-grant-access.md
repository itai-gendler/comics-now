---
appliesTo:
- type: entity
  id: access-grant
  effect: creates
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/admin/users.js
---

# Only admins grant access

Which libraries, publishers, series, folders and comics a user may read is set by admins alone.
