---
appliesTo:
- type: capability
  id: run-tagging-scan
- type: entity
  id: pending-match
  effect: creates
references:
- kind: code
  role: implementation
  target: tagger/app.py
- kind: code
  role: implementation
  target: server/services/tagger.js#runComicTagger
---

# A match is applied at the auto-accept confidence, reviewed between the two confidences, and rejected below the review confidence

Tagging applies the best match itself when its confidence reaches the auto-accept confidence (90% by default), holds the comic for an admin's review when it reaches only the review confidence (80% by default), and records the comic as unmatched below that.
