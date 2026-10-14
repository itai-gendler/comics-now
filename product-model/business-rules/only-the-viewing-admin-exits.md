---
appliesTo:
- type: entity
  id: impersonation
  effect: changes
permits:
- related:
  - verb: starts
    entity: admin
references:
- kind: code
  role: implementation
  target: server/routes/admin/impersonate.js
---

# Only the admin who started viewing as a user ends it

The banner's Exit Impersonation belongs to the admin who chose Login as.
