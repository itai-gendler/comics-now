---
domain: devices
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: public/js/settings/devices.js
- kind: code
  role: implementation
  target: server/routes/user/devices.js
---

# View devices

A person sees the devices they have read on in Settings → Devices; an admin can pick any user to see theirs.
