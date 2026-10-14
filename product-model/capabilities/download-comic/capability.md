---
domain: downloads
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: public/js/offline/download-actions.js#downloadComic
- kind: code
  role: implementation
  target: public/js/offline/downloads.js
- kind: code
  role: implementation
  target: server/routes/user/pages.js
- kind: doc
  role: context
  target: README.md
---

# Download for offline

On a phone or tablet a person queues a comic, a series, a reading list or a publisher for offline reading; the browser downloads them in the background, resuming interrupted transfers, and keeps them for reading without a connection.
