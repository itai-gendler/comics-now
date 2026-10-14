---
appliesTo:
- type: capability
  id: create-reading-list
- type: capability
  id: edit-reading-list
- type: entity
  id: reading-list
  facts:
  - Name
references:
- kind: code
  role: implementation
  target: server/routes/user/reading-lists.js
---

# A reading list always has a name

Creating or renaming a list without a name is refused.
