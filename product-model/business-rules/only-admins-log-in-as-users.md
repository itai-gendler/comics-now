---
appliesTo:
- type: entity
  id: impersonation
  effect: creates
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/admin/impersonate.js
- kind: code
  role: implementation
  target: server/middleware/impersonation.js
---

# Only an admin logs in as a user, and never as another admin or themselves

Viewing the library as someone is an admin's check on what a user sees.
