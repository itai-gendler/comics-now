---
appliesTo:
- type: capability
  id: run-guided-detection
- type: entity
  id: server-settings
  facts:
  - Guided auto-run
references:
- kind: code
  role: implementation
  target: server/services/guided-reader.js#onLibraryScanComplete
---

# Automatic detection after a scan covers only the comics that scan added

When automatic processing is on, detection after a library scan runs on just the comics that scan added, never on the older pending backlog.
