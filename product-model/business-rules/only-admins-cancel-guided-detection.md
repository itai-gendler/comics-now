---
appliesTo:
- type: entity
  id: guided-detection-run
  effect: changes
permits:
- actors:
  - admin
- unattended: true
references:
- kind: code
  role: implementation
  target: server/services/guided-reader.js#cancelAll
---

# Only admins and the server end a Guided Detection run

An admin cancels a run; otherwise the server ends it when its queue is empty.
