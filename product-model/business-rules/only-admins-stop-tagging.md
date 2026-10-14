---
appliesTo:
- type: entity
  id: tagging-scan
  effect: changes
permits:
- actors:
  - admin
- unattended: true
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#cancelComicTagger
---

# Only admins and the server itself end a tagging scan

An admin cancels a running scan; otherwise the server finishes it.
