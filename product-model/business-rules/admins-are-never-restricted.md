---
appliesTo:
- type: entity
  id: access-grant
  effect: creates
- type: capability
  id: grant-access
references:
- kind: code
  role: implementation
  target: server/routes/admin/users.js
---

# Admins hold no access grants and read everything

Permissions are kept only for users; an admin's permissions cannot be set.
