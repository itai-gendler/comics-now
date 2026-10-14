---
domain: reading-lists
availability:
- place: web::library
- place: mcp
references:
- kind: code
  role: implementation
  target: server/routes/user/reading-lists.js
- kind: code
  role: implementation
  target: server/services/readingLists.js#syncDefaultReadingLists
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Create a reading list

A person names a new reading list, empty or starting with chosen comics. A list made by the built-in account becomes a default list that every user also receives.
