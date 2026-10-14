---
appliesTo:
- type: entity
  id: reading-preference
- type: capability
  id: read-comic
references:
- kind: code
  role: implementation
  target: server/db.js#resolveReadingModes
---

# The most specific reading preference decides how a comic reads

A comic's own choice beats its series', its series' beats its publisher's, and its publisher's beats its library's; with no choice anywhere a comic reads left to right, page by page.
