---
domain: library
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: public/js/viewer/fullscreen.js
- kind: code
  role: implementation
  target: public/js/sync.js
- kind: code
  role: implementation
  target: server/routes/user/progress.js
- kind: code
  role: implementation
  target: public/js/viewer/viewer-local.js
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Read a comic

A person reads a comic page by page, as one continuous scroll, right to left, or panel by panel in Guided View, and the Product saves where they reached for this device and for the person. Comics downloaded to the browser and comics in a device library are read the same way without the server.
