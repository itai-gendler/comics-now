---
appliesTo:
- type: capability
  id: sign-out
- type: entity
  id: downloaded-comic
  effect: removes
references:
- kind: code
  role: implementation
  target: public/js/auth.js#handleLogout
---

# Signing out removes every comic downloaded in that browser

Logging out clears the browser's stored data, downloaded comics included.
