---
domain: users
relations: []
references:
- kind: code
  role: implementation
  target: server/middleware/impersonation.js
- kind: code
  role: implementation
  target: server/routes/admin/impersonate.js
---

# Impersonation

An admin viewing the library as a particular user ("Login as"), seeing exactly their access, progress and lists, until the admin exits.

## Information kept

- **Started** — when the admin began viewing as the user

## States

### Active

The admin sees the library as the user.

### Ended

The admin has exited and sees their own library again.
