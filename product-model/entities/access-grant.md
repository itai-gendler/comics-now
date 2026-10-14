---
domain: users
references:
- kind: code
  role: implementation
  target: server/access-control.js#checkComicAccess
- kind: code
  role: implementation
  target: server/routes/admin/users.js
---

# Access Grant

One entry of a user's permissions: a library, publisher, series, folder or single comic the user may read, and whether it also opens everything beneath it, including publishers and series added later.

## Information kept

- **Level** — Library, Publisher, Series, Folder or Comic
- **Target** — the library, publisher, series, folder or comic it names
- **Includes everything below** — whether it also opens every publisher, series, folder or comic beneath the target
