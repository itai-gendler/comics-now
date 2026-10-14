---
domain: library
availability:
- place: web::library
- place: mcp
references:
- kind: code
  role: implementation
  target: server/routes/user/library.js
- kind: code
  role: implementation
  target: public/js/library/search.js
---

# Search the library

A person searches titles, series, publishers and the rest of the metadata, then narrows by read status and sorts. Only comics the person may read are returned.
