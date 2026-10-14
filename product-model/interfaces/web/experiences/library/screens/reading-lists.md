---
entities:
- entity: reading-list
  shows:
  - Name
  - Description
  - Position
  - Progress
  collects:
  - Name
  - Description
references:
- kind: code
  role: implementation
  target: public/js/reading-lists.js
---

# Reading Lists

The person's reading lists with their progress, searchable and filterable by publisher, with create, import and export.
