---
appliesTo:
- type: capability
  id: log-in-as-user
- type: capability
  id: exit-impersonation
- type: context
  context:
    place: web::library
references:
- kind: code
  role: implementation
  target: server/middleware/impersonation.js#impersonationReadOnlyGuard
---

# Nothing can be changed while an admin views the library as a user

While an impersonation is active every attempt to change something is refused with "Read-only while impersonating a user", so the user never sees side effects; only exiting is allowed.
