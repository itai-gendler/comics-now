---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin ticks the series a user may read and saves
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
- text: The Product records an access grant for each series
  kind: product
  actor: admin
  entities:
  - entity: access-grant
    effect: creates
    facts:
    - Level
    - Target
    - Includes everything below
  contexts:
    web:
      place: web::administration::user-permissions
---

# Open single series to a user

## Trigger

An admin wants a child to read only a few series.

## Outcome

The user can read just those series.
