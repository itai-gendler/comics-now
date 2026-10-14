---
references:
- kind: code
  role: implementation
  target: server/middleware/auth.js#recordUserActivity
- kind: code
  role: implementation
  target: server/db.js#initializeDatabase
---

# Account

The record of one person who has signed in to the server, whichever role they hold. The Product creates it the first time the person arrives and keeps it up to date on later visits.

## Information kept

- **Email** — the address the person signs in with
- **Built-in** — whether this is the server's built-in local account, used from trusted networks and when sign-in is off
- **Joined** — when the person first reached the server
- **Last seen** — when the person last used the server
