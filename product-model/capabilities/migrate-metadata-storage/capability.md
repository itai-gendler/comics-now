---
domain: tag-comics-now
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/library-mgmt.js
---

# Migrate existing comics

An admin moves every comic's saved metadata to the chosen storage: into the CBZ archives, into sidecar files, or into the database only, cleaning up the other places.
