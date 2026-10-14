---
domain: management
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
- kind: code
  role: implementation
  target: server/services/organization.js#formatFolderPath
- kind: code
  role: implementation
  target: server/services/organization.js#updateComicIdentity
---

# Move comics

An admin files successfully tagged comics into folders by the folder rules: from the Smart Inbox into a chosen library, or reorganizing a whole library in place after typing a confirmation phrase. Progress, lists, covers and Guided Views follow each comic.
