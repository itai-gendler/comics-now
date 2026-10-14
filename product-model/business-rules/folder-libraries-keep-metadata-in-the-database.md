---
appliesTo:
- type: capability
  id: edit-comic-metadata
- type: entity
  id: comic
  effect: changes
  facts:
  - Summary
references:
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
---

# Metadata saved for a comic in a folder library stays in the database

Saving a comic's metadata in a library organized by folder never writes ComicInfo into or beside the file; in a metadata library it is written where the server keeps metadata.
