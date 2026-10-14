---
domain: general
relations:
- entity: comic
  verb: holds
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/config.js#addLibrary
- kind: code
  role: implementation
  target: server/routes/admin/settings.js
---

# Library

A folder on the server that the Product reads comics from, organized either by the metadata inside each comic or by its folders on disk. Comics waiting in the Smart Inbox belong to no library.

## Information kept

- **Folder** — the folder on the server the comics are read from
- **Organization** — Metadata, grouping comics as publisher, series and issue from their ComicInfo, or Folder, mirroring the folders on disk
