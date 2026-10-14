---
domain: users
availability:
- place: web::administration
- place: web::library
references:
- kind: code
  role: implementation
  target: server/routes/admin/impersonate.js
- kind: code
  role: implementation
  target: public/js/impersonation.js#startImpersonation
- kind: code
  role: implementation
  target: server/middleware/impersonation.js
- kind: doc
  role: context
  target: docs/API.md
---

# Log in as a user

An admin chooses Login as on a user and the whole app reloads as that user, with their access, progress and lists, so the admin can check what they see. Nothing can be changed while viewing as the user.
