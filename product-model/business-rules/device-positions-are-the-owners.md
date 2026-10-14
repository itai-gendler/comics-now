---
appliesTo:
- type: entity
  id: device
  effect: changes
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
  target: server/routes/user/progress.js
---

# A device's reading positions change only for its owner

Reading on a device updates that device's positions only when the device is the reader's own.
