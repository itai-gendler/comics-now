---
appliesTo:
- type: entity
  id: device
  effect: creates
references:
- kind: code
  role: implementation
  target: server/routes/user/devices.js
- kind: code
  role: implementation
  target: server/routes/user/progress.js
---

# A device belongs to the person who registered it

A device id already registered to one person is not registered to another, and each person sees only their own devices' positions when continuing.
