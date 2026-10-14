---
appliesTo:
- type: capability
  id: change-gemini-settings
- type: entity
  id: server-settings
  facts:
  - Gemini cover matching
  - Gemini agreement
references:
- kind: code
  role: implementation
  target: server/routes/admin/gemini.js
- kind: code
  role: implementation
  target: server/services/gemini-tagger.js#installTaggerHook
---

# Gemini cover matching stays off until the compliance agreement is accepted

Entering a Gemini key or turning cover matching on is refused until an admin accepts the Gemini compliance agreement, and tagging never calls Gemini without it.
