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
  target: public/js/settings/users.js
---

# View users

An admin sees everyone who has signed in to the server, with role, when they joined and when they were last seen.
