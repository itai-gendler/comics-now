---
entities:
- entity: comic
  shows:
  - Page count
- entity: reading-progress
  shows:
  - Last read page
- entity: guided-view
  shows:
  - Panels
- entity: device
  shows:
  - Name
  - Reading positions
- entity: downloaded-comic
  shows:
  - Pages
references:
- kind: code
  role: implementation
  target: public/js/viewer/fullscreen.js
- kind: code
  role: implementation
  target: public/js/sync.js
---

# Reader

The comic being read, full screen: page by page, as one continuous scroll, right to left, or panel by panel in Guided View, with the page preview grid and the offer to continue from another device.
