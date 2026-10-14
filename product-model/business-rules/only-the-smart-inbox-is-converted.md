---
appliesTo:
- type: capability
  id: scan-library
- type: entity
  id: comic
  effect: creates
references:
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
- kind: code
  role: implementation
  target: server/services/library-conversion.js
---

# PDF and CBR files are converted to CBZ only in the Smart Inbox

A scan converts PDF files, and CBR files when CBR is not allowed, into CBZ only when they sit in the Smart Inbox; elsewhere they are left alone.
