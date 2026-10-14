---
entities:
- entity: device
  shows:
  - Name
  - Browser
  - Registered
  - Last seen
- entity: account
  shows:
  - Email
references:
- kind: code
  role: implementation
  target: public/js/settings/devices.js
---

# Devices

The devices a person has read on, when each was registered and last seen; admins can pick any user's devices.
