---
appliesTo:
- type: entity
  id: reading-list
  effect: creates
- type: entity
  id: account
  facts:
  - Built-in
references:
- kind: code
  role: implementation
  target: server/services/readingLists.js#syncDefaultReadingLists
- kind: code
  role: implementation
  target: server/routes/user/reading-lists.js
---

# Reading lists of the built-in account are every user's default lists

A list created by the built-in account is copied, with its comics in order, to every other person, and every person arriving for the first time receives a copy of each; a person who already has a list of that name keeps theirs.
