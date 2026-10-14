---
appliesTo:
- type: capability
  id: rename-comics
- type: capability
  id: move-comics
references:
- kind: code
  role: implementation
  target: server/routes/admin/rename.js
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
---

# Renaming or reorganizing a whole library needs the typed phrase "i want to do this"

Working on the Smart Inbox needs no confirmation; renaming or reorganizing every comic of a library is refused unless the admin types the exact phrase.
