---
appliesTo:
- type: entity
  id: account
  facts:
  - Email
- type: entity
  id: server-settings
  facts:
  - Admin email
references:
- kind: code
  role: implementation
  target: server/middleware/auth.js#extractUserFromJWT
- kind: code
  role: implementation
  target: server/config.js#getAdminEmail
---

# The Admin is the person whose email is the server's configured admin email

Every time a person arrives through Cloudflare Access their role is set from the configured admin email: that email is the Admin, everyone else is a User. The built-in account is always an admin.
