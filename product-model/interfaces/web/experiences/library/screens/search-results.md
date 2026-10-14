---
entities:
- entity: comic
  shows:
  - Title
  - Series
  - Publisher
  - Issue number
  - Year
  - Cover
- entity: reading-progress
  shows:
  - Last read page
references:
- kind: code
  role: implementation
  target: public/js/library/search.js
---

# Search results

Comics matching a search across titles, series, publishers and other metadata, with status filters and sorting.
