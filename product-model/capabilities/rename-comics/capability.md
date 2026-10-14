---
domain: management
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/rename.js
- kind: code
  role: implementation
  target: server/services/organization.js#formatComicFilename
---

# Rename comics

An admin renames successfully tagged comics by the naming rules: the comics in the Smart Inbox, or every comic in a chosen library after typing a confirmation phrase.
