---
appliesTo:
- type: entity
  id: guided-view
  effect: changes
permits:
- actors:
  - admin
- unattended: true
- related:
  - verb: has
    entity: comic
  - verb: holds
    entity: library
  - verb: manages
    entity: admin
  - verb: connects
    entity: ai-agent
references:
- kind: code
  role: implementation
  target: server/services/guided-reader.js#runWorker
- kind: code
  role: implementation
  target: server/routes/admin/mcp-tools.js
---

# A Guided View changes only through detection or an admin's AI agent

Guided Views are made by the panel detector, run by an admin or by the server, or written by an AI agent an admin connected.
