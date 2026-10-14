---
appliesTo:
- type: entity
  id: reading-list
  effect: creates
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
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/user/reading-lists.js
---

# A person creates their own reading lists; an admin may also create them for others

A reading list belongs to the person who made it, or to the admin whose AI agent made it. An admin may also create lists for every user, as when a default list is given to everyone.
