---
domain: tag-comics-now
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#skipCurrentMatch
---

# Skip a match

An admin rejects every candidate for the waiting comic; it is recorded as unmatched and tagging moves on.
