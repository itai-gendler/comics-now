---
appliesTo:
- type: entity
  id: server-settings
  effect: changes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/admin/settings.js
- kind: code
  role: implementation
  target: server/routes/admin/comictagger.js
- kind: code
  role: implementation
  target: server/routes/admin/guided.js
- kind: code
  role: implementation
  target: server/routes/admin/gemini.js
---

# Only admins and the server change the server's settings

Every section of the server's settings is changed by admins; the server itself only counts Gemini requests.
