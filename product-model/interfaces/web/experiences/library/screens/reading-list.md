---
entities:
- entity: reading-list
  shows:
  - Name
  - Description
  - Comics
  - Progress
  collects:
  - Name
  - Description
- entity: comic
  shows:
  - Title
  - Series
  - Issue number
  - Cover
- entity: reading-progress
  shows:
  - Last read page
references:
- kind: code
  role: implementation
  target: public/js/reading-lists.js
---

# Reading list

One reading list: its comics in reading order with each one's progress.
