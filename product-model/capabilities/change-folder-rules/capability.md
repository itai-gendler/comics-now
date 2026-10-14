---
domain: management
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/comictagger.js
- kind: code
  role: implementation
  target: server/services/organization.js#formatFolderPath
---

# Change folder rules

An admin sets the folder levels comics are filed under, such as publisher then series and volume, with a live preview.
