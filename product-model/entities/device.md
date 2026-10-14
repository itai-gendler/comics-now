---
domain: devices
references:
- kind: code
  role: implementation
  target: server/routes/user/devices.js
- kind: code
  role: implementation
  target: public/js/sync.js
---

# Device

A browser or installed app a person reads on. The Product registers it the first time it connects and remembers where it reached in each comic, so another device can offer to continue from there.

## Information kept

- **Name** — the readable name, such as iPad Pro - Safari
- **Browser** — the browser it identifies itself as
- **Registered** — when it first connected
- **Last seen** — when it last connected
- **Reading positions** — the page this device last reached in each comic, and when
