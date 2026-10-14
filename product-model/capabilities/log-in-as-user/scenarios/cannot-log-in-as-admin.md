---
kind: validation
routes:
  web: Web
steps:
- text: The Admin chooses Login as on an admin account
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::administration::users
- text: The Product refuses to view as an admin
  kind: condition
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::users
---

# Another admin cannot be viewed

## Trigger

An admin chooses Login as on an admin account, or on themselves.

## Outcome

Nothing changes.
