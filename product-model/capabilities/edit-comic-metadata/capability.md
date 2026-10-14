---
domain: library
availability:
- place: web::library
- place: mcp
references:
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
- kind: code
  role: implementation
  target: server/routes/admin/mcp-tools.js
- kind: code
  role: implementation
  target: public/js/metadata.js
- kind: code
  role: implementation
  target: server/services/metadata.js
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Edit a comic's metadata

An admin corrects a comic's metadata in its Metadata tab, optionally filling it from a ComicVine lookup, and saves it to the database and to where the server keeps metadata. An AI agent writes tags the same way after inspecting the cover.
