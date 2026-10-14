---
domain: general
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
- kind: code
  role: implementation
  target: server/services/library-conversion.js
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Scan the libraries

The Product walks every library and the Smart Inbox for CBZ (and, when allowed, CBR) files, adds new comics with their metadata, cover and page count, updates changed ones and drops comics whose files are gone. It scans on its interval, and an admin can scan now or force a full rescan.
