---
domain: devices
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: server/routes/user/devices.js
- kind: code
  role: implementation
  target: public/js/sync.js
---

# Register a device

The first time a browser or installed app connects, the Product registers it to the person under a readable name; a browser it recognizes keeps its earlier registration.
