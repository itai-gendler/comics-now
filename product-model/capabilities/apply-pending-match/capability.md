---
domain: tag-comics-now
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#applyUserSelection
---

# Apply a match

An admin compares the waiting comic's first page with its candidate matches and applies one; its tags are written and tagging moves on.
