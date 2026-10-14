---
domain: users
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: public/js/impersonation.js#stopImpersonation
- kind: code
  role: implementation
  target: server/routes/admin/impersonate.js
---

# Exit impersonation

An admin viewing as a user chooses Exit Impersonation in the banner and returns to their own library.
