---
entities:
- entity: server-settings
  shows:
  - Naming rules
  - Folder rules
  collects:
  - Naming rules
  - Folder rules
- entity: comic
  shows:
  - File name
  - Location
- entity: library
  shows:
  - Folder
references:
- kind: code
  role: implementation
  target: public/js/settings/comics-management.js
---

# Management

Filing comics: renaming and moving tagged comics from the Smart Inbox, renaming or reorganizing a whole library, the naming and folder rules with live previews, and the errors those operations hit.
