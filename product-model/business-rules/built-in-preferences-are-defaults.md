---
appliesTo:
- type: entity
  id: reading-preference
- type: entity
  id: account
  facts:
  - Built-in
references:
- kind: code
  role: implementation
  target: server/db.js#getReadingPrefMaps
- kind: code
  role: implementation
  target: server/db.js#resolveReadingModes
---

# The built-in account's reading preferences are every person's defaults

Where a person has made no choice of their own for a comic, series, publisher or library, the built-in account's choice applies to them.
