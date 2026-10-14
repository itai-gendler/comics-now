---
appliesTo:
- type: entity
  id: comic
  effect: changes
permits:
- actors:
  - admin
- unattended: true
- related:
  - verb: holds
    entity: library
  - verb: manages
    entity: admin
  - verb: connects
    entity: ai-agent
references:
- kind: code
  role: implementation
  target: server/routes/index.js
- kind: code
  role: implementation
  target: server/middleware/auth.js#requireAdmin
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
---

# Only admins, their AI agents and the server's own runs change a comic

A comic's metadata, tag status, name and location change only through an admin (editing, tagging, renaming, moving), an AI agent an admin connected, or the scans and tagging the server runs on its own schedule. Users only read.
