---
appliesTo:
- type: capability
  id: rename-comics
- type: capability
  id: move-comics
- type: entity
  id: comic
  effect: changes
  facts:
  - File name
  - Location
references:
- kind: code
  role: implementation
  target: server/routes/admin/rename.js
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
---

# Only Successful comics are renamed or moved

Renaming and moving pick up only comics whose tags are complete; comics still Pending or Failed stay where and as they are.
