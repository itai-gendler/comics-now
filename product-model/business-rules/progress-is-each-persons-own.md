---
appliesTo:
- type: entity
  id: reading-progress
  effect: changes
permits:
- related:
  - verb: keeps
    entity: user
- related:
  - verb: keeps
    entity: admin
- related:
  - verb: keeps
    entity: admin
  - verb: connects
    entity: ai-agent
references:
- kind: code
  role: implementation
  target: server/routes/user/progress.js
---

# Reading progress changes only for the person it belongs to

Reading, marking read and marking unread change only the acting person's progress, or the progress of the admin whose AI agent acts.
