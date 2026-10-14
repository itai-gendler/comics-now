---
kind: primary
routes:
  web: Web
steps:
- text: The Admin unticks a publisher in a user's permissions and saves
  kind: actor
  actor: admin
  entities:
  - entity: access-grant
    effect: reads
    facts:
    - Level
    - Target
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::user-permissions
- text: The Product removes the access grant
  kind: product
  actor: admin
  entities:
  - entity: access-grant
    effect: removes
  contexts:
    web:
      place: web::administration::user-permissions
---

# Close a publisher to a user

## Trigger

An admin no longer wants a user reading a publisher.

## Outcome

The user no longer sees that publisher's comics.
