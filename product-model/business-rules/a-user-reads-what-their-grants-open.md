---
appliesTo:
- type: entity
  id: comic
  effect: reads
references:
- kind: code
  role: implementation
  target: server/access-control.js#checkComicAccess
- kind: code
  role: implementation
  target: server/routes/user/library.js
- kind: code
  role: implementation
  target: server/routes/user/pages.js
- kind: doc
  role: intent
  target: docs/WIKI.md
---

# A user sees only the comics their access grants open

An admin sees every comic. A user sees a comic in a metadata library when a grant opens its library with everything below it, its publisher with everything below it (in any library), or its series; in a folder library, when a grant opens the library and the comic itself, its folder, or a folder above it with everything below it. Browsing, search, details, pages and downloads all follow the same grants.
