---
appliesTo:
- type: capability
  id: download-comic
- type: entity
  id: downloaded-comic
  effect: creates
references:
- kind: code
  role: implementation
  target: public/js/offline/download-actions.js#downloadComic
- kind: code
  role: implementation
  target: public/js/context-menu/actions-shared.js
---

# Comics are downloaded for offline reading only on phones and tablets

Download actions are offered and allowed only on mobile devices; on a desktop the Product explains and queues nothing.
