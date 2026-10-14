---
entities:
- entity: downloaded-comic
  shows:
  - Progress
  - Size
- entity: comic
  shows:
  - Title
  - Series
references:
- kind: code
  role: implementation
  target: public/js/offline/downloads.js
---

# Downloads

The download queue: each comic queued, downloading, downloaded or failed, with its progress.
