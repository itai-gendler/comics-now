---
kind: validation
routes:
  web: Web
steps:
- text: The Admin saves permissions for an admin account
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::administration::user-permissions
- text: The Product refuses because admins have full access
  kind: condition
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::user-permissions
---

# Admins cannot be restricted

## Trigger

An admin tries to set permissions for an account that holds the Admin role.

## Outcome

Nothing is saved; admins read everything.
