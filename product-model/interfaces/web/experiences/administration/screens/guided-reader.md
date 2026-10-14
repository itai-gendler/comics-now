---
entities:
- entity: guided-detection-run
  shows:
  - Scope
  - Current comic
  - Queue
- entity: guided-view
  shows:
  - Error
- entity: server-settings
  shows:
  - Guided auto-run
  - Guided schedule
  collects:
  - Guided auto-run
  - Guided schedule
references:
- kind: code
  role: implementation
  target: public/js/guided-reader.js
---

# Guided Reader

Guided View detection: how many comics are pending, processing, completed and failed, the current run and its live log, and the automatic processing settings.
