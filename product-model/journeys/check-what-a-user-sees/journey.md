---
actors:
- admin
references:
- kind: code
  role: implementation
  target: public/js/impersonation.js
- kind: code
  role: implementation
  target: server/routes/admin/impersonate.js
---

# Check what a user sees

## Goal

An admin confirms a user's permissions by looking at the library exactly as that user does, then returns to their own view.

## Success criterion

The admin has browsed the library as the user and is back in their own library.
