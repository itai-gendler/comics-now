---
entities:
- entity: reading-progress
  shows:
  - Last read page
  - Page count
  - Updated
- entity: comic
  shows:
  - Title
  - Series
- entity: account
  shows:
  - Email
references:
- kind: code
  role: implementation
  target: public/js/settings/user-stats.js
---

# User stats

One user's reading figures over a chosen window: comics opened, completed and in progress, active days, a per-day chart and recent activity, all derived from saved progress.
