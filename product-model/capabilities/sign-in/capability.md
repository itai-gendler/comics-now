---
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: server/middleware/auth.js#extractUserFromJWT
- kind: code
  role: implementation
  target: server/services/readingLists.js#autoSeedNewUserReadingLists
- kind: doc
  role: intent
  target: docs/WIKI.md
---

# Sign in

A person arrives through Cloudflare Access and the Product recognizes them by the identity Access vouches for, creating their account on the first visit. From a trusted network, or when sign-in is off, the person uses the built-in admin account instead.
