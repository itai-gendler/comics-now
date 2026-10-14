---
entities:
- entity: reading-preference
  shows:
  - Level
  - Target
  - Manga mode
  - Continuous mode
  collects:
  - Manga mode
  - Continuous mode
- entity: library
  shows:
  - Folder
references:
- kind: code
  role: implementation
  target: public/js/settings/comics-defaults.js
---

# Comics defaults

The person's default reading direction and scroll mode, for every library and for each library.
