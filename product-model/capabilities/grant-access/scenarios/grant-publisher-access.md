---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Edit Permissions on a user
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::users
- text: The Admin ticks a publisher with everything below it and saves
  kind: actor
  actor: admin
  entities:
  - entity: access-grant
    effect: reads
    facts:
    - Level
    - Target
    - Includes everything below
  contexts:
    web:
      place: web::administration::user-permissions
- text: The Product records the access grant for the user
  kind: product
  actor: admin
  entities:
  - entity: access-grant
    effect: creates
    facts:
    - Level
    - Target
    - Includes everything below
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::user-permissions
---

# Open a publisher to a user

## Trigger

An admin wants a family member to read everything from one publisher.

## Outcome

The user can read every comic of that publisher in any library, including ones added later.

## Edge cases

- A series ticked under a publisher that is already open with everything below it is not kept separately.
