---
appliesTo:
- type: capability
  id: scan-library
- type: entity
  id: comic
  effect: removes
references:
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
- kind: doc
  role: intent
  target: docs/WIKI.md
---

# No comic is removed by a scan that could not read every folder

If any library folder or sub-folder could not be read, the scan removes no comics at all, so a disconnected drive never costs anyone their progress or reading lists.
