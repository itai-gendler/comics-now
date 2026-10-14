---
appliesTo:
- type: entity
  id: pending-match
  effect: creates
permits:
- actors:
  - admin
- unattended: true
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#runComicTagger
---

# Only tagging holds a comic for review

A pending match is created only by a tagging scan, whether an admin started it or the schedule did.
