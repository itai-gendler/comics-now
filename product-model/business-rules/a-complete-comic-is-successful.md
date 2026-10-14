---
appliesTo:
- type: entity
  id: comic
  effect: changes
  to: Successful
- type: entity
  id: comic
  effect: changes
  to: Failed
references:
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
- kind: code
  role: implementation
  target: server/services/tagger.js
---

# A comic is Successful exactly when it has a series, a publisher, a date and an issue number

Scans, tagging and metadata saves all judge a comic the same way: with all four present it is Successful, otherwise a save or a tagging attempt leaves it Failed.
