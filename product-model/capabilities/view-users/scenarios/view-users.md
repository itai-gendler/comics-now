---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens Users
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
    - Joined
    - Last seen
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::users
---

# See who uses the server

## Trigger

An admin opens Settings → Users.

## Outcome

The admin sees every account.
