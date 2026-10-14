---
appliesTo:
- type: capability
  id: run-tagging-scan
- type: entity
  id: server-settings
  facts:
  - Smart Inbox folder
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#runComicTagger
---

# Tagging works only on the comic files at the top of the Smart Inbox

Tag Comics Now! looks only at the CBZ (and, when allowed, CBR) files directly in the Smart Inbox folder; comics already in libraries are corrected one at a time from their details.
