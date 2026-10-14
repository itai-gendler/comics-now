---
appliesTo:
- type: entity
  id: reading-list
  effect: removes
permits:
- related:
  - verb: owns
    entity: user
- related:
  - verb: owns
    entity: admin
references:
- kind: code
  role: implementation
  target: server/routes/user/reading-lists.js
---

# Only its owner deletes a reading list

Deleting a list removes only that person's list; copies other people received stay.
