---
domain: users
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/user-stats.js
- kind: code
  role: implementation
  target: public/js/settings/user-stats.js
---

# View user stats

An admin sees how much a user reads over a window of days: comics opened, completed and in progress, active days, a per-day chart and recent activity. Everything is derived from saved progress; time spent reading is not tracked.
