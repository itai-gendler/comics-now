---
domain: users
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/users.js
- kind: code
  role: implementation
  target: public/js/settings/user-access.js
---

# Revoke access

An admin unticks a library, publisher, series, folder or comic in a user's permissions and saves, closing it to the user.
