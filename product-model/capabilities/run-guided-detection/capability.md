---
domain: guided-reader
availability:
- place: web::administration
- place: web::library
- place: mcp
references:
- kind: code
  role: implementation
  target: server/services/guided-reader.js#startRun
- kind: code
  role: implementation
  target: server/services/guided-reader.js#startRunForScope
- kind: code
  role: implementation
  target: server/services/guided-reader.js#onLibraryScanComplete
- kind: code
  role: implementation
  target: server/services/panel-detector.js
- kind: code
  role: implementation
  target: server/routes/admin/guided.js
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Run Guided Detection

The panel detector makes Guided Views, in library, publisher, series and issue order. An admin runs it on every pending and failed comic, or on one comic, series, publisher or library from its menu, optionally re-running comics that already have one; it also runs on newly added comics and on a schedule when those are on; an AI agent can trigger it too.
