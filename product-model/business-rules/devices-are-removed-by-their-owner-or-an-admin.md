---
appliesTo:
- type: entity
  id: device
  effect: removes
permits:
- related:
  - verb: owns
    entity: user
- related:
  - verb: owns
    entity: admin
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/user/devices.js
---

# A device is removed by its owner or an admin

People remove their own devices; admins can remove anyone's.
