---
appliesTo:
- type: capability
  id: scan-library
- type: capability
  id: run-tagging-scan
references:
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
---

# Only a full scan runs while tagging is running

While a tagging scan is working through the Smart Inbox, scheduled and ordinary scans are skipped; a full scan an admin starts still runs.
