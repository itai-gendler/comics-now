---
domain: general
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/settings.js
- kind: code
  role: implementation
  target: server/validation.js#validateScanInterval
---

# Change general settings

An admin sets the scan interval, the ComicVine API key, which formats the libraries include and where saved metadata goes.
