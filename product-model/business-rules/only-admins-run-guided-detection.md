---
appliesTo:
- type: entity
  id: guided-detection-run
  effect: creates
permits:
- actors:
  - admin
- unattended: true
- related:
  - verb: starts
    entity: admin
  - verb: connects
    entity: ai-agent
references:
- kind: code
  role: implementation
  target: server/routes/admin/guided.js
- kind: doc
  role: intent
  target: docs/WIKI.md
---

# Only admins, their AI agents and the server's own settings start Guided Detection

Panel detection is heavy, so only admins start it (from Guided Reader or a menu), an AI agent an admin connected, or the server when automatic processing or the schedule is on. Every reader of a comic then shares its Guided View.
