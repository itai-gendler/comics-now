---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin ticks the library and folders in a folder library and saves
  kind: actor
  actor: admin
  entities:
  - entity: access-grant
    effect: reads
    facts:
    - Level
    - Target
    - Includes everything below
  - entity: library
    effect: reads
    facts:
    - Organization
  contexts:
    web:
      place: web::administration::user-permissions
- text: The Product records an access grant for the library and for each folder
  kind: product
  actor: admin
  entities:
  - entity: access-grant
    effect: creates
    facts:
    - Level
    - Target
    - Includes everything below
  - entity: library
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::user-permissions
---

# Open folders in a folder library

## Trigger

An admin shares part of a library organized by folder.

## Outcome

The user can read the comics in the ticked folders, and below them where everything below was ticked.
