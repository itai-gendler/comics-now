---
entities:
- entity: access-grant
  shows:
  - Level
  - Target
  - Includes everything below
  collects:
  - Level
  - Target
  - Includes everything below
- entity: account
  shows:
  - Email
- entity: library
  shows:
  - Folder
  - Organization
references:
- kind: code
  role: implementation
  target: public/js/settings/user-access.js
---

# User permissions

One user's permissions as a tree of libraries, publishers and series (or folders and comics in folder libraries), each ticked for the item alone or for everything below it.
