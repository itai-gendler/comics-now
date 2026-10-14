---
entities:
- entity: comic
  shows:
  - Title
  - Series
  - Publisher
  - Issue number
  - Volume
  - Year
  - Creators
  - Summary
  - Cover
  - Page count
  collects:
  - Title
  - Series
  - Publisher
  - Issue number
  - Volume
  - Year
  - Creators
  - Summary
- entity: reading-progress
  shows:
  - Last read page
  - Page count
- entity: reading-preference
  shows:
  - Manga mode
references:
- kind: code
  role: implementation
  target: public/js/metadata.js
- kind: code
  role: implementation
  target: public/js/viewer/ui-summary.js
---

# Comic details

One comic: its cover, metadata, reading position, Guided View status and actions; admins edit its metadata here.
