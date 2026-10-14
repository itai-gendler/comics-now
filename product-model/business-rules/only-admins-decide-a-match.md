---
appliesTo:
- type: entity
  id: pending-match
  effect: changes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#applyUserSelection
- kind: code
  role: implementation
  target: server/services/tagger.js#skipCurrentMatch
---

# Only an admin applies or skips a pending match

A comic held for review waits until an admin applies a candidate or skips it.
