---
availability:
- place: web::library
references:
- kind: code
  role: implementation
  target: public/js/settings/comics-defaults.js
- kind: code
  role: implementation
  target: server/routes/user/reading.js
---

# Change comics defaults

In Settings → Comics Defaults a person sets their default reading direction and scroll mode for every library, or for one library. Saving a default clears the person's more specific choices under it.
