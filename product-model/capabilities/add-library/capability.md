---
domain: general
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/settings.js
- kind: code
  role: implementation
  target: server/config.js#addLibrary
- kind: code
  role: implementation
  target: public/js/settings.js
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Add a library

An admin adds a folder on the server as a library and chooses whether it is organized by metadata or by its folders.
