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
  target: server/access-control.js#checkComicAccess
- kind: code
  role: implementation
  target: public/js/settings/user-access.js
- kind: doc
  role: intent
  target: docs/WIKI.md
---

# Grant access

An admin opens a user's permissions and ticks a library, publisher or series (or a folder or comic in a folder library), either for that item alone or for everything below it, including what is added later, and saves.
