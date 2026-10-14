---
domain: library
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: server/services/library.js#buildLibrary
- kind: code
  role: implementation
  target: server/routes/user/library.js
- kind: code
  role: implementation
  target: public/js/library/smartlists.js
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Browse the library

A person moves through the libraries open to them: library, publisher, series and issues in a metadata library, folders and files in a folder library, and the smart lists of recently added, downloaded, guided and manga comics.
