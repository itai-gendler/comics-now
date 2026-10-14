---
domain: tag-comics-now
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#cancelComicTagger
---

# Cancel a tagging scan

An admin stops a running tagging scan. A comic waiting for review stays reviewable.
