---
references:
- kind: code
  role: implementation
  target: server/routes/user/progress.js
- kind: code
  role: implementation
  target: server/db.js#initializeDatabase
---

# Reading Progress

How far one person has read one comic, the same on every device they use. A comic is unread at the first page, in progress past it, and completed at its last page; reading lists, badges, filters and user stats are all read from it.

## Information kept

- **Last read page** — the page the person last reached
- **Page count** — the comic's page count when progress was saved
- **Updated** — when it last changed
