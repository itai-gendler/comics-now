---
entities:
- entity: comic
  shows:
  - Series
  - Issue number
  - Title
  - Year
  - Cover
- entity: reading-progress
  shows:
  - Last read page
  - Page count
references:
- kind: code
  role: implementation
  target: public/js/library/render.js
---

# Series

One series: its issues with covers, numbers, read badges and Guided View status.
