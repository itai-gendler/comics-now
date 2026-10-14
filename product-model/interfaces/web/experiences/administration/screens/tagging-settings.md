---
entities:
- entity: server-settings
  shows:
  - Tagging schedule
  - Smart Inbox folder
  - Metadata storage
  - Auto-accept confidence
  - Review confidence
  - Enabled sources
  - Re-scan tagged comics
  - Source credentials
  - ComicVine API key
  - Tagger service port
  collects:
  - Tagging schedule
  - Smart Inbox folder
  - Metadata storage
  - Auto-accept confidence
  - Review confidence
  - Enabled sources
  - Re-scan tagged comics
  - Source credentials
  - ComicVine API key
  - Tagger service port
references:
- kind: code
  role: implementation
  target: public/js/comictagger.js
---

# Tagging settings

Tag Comics Now! settings: schedule, Smart Inbox folder, metadata storage, confidence thresholds, sources and their credentials, service port.
