---
appliesTo:
- type: entity
  id: reading-list
  effect: changes
permits:
- related:
  - verb: owns
    entity: user
- related:
  - verb: owns
    entity: admin
- related:
  - verb: owns
    entity: admin
  - verb: connects
    entity: ai-agent
references:
- kind: code
  role: implementation
  target: server/routes/user/reading-lists.js
---

# Only its owner changes a reading list

Renaming, filling, emptying and reordering a list are for the person it belongs to, or the AI agent of the admin it belongs to.
