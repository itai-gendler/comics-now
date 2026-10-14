---
kind: validation
routes:
  web: Web
steps:
- text: The Admin enters a folder that is already a library and chooses Add
  kind: actor
  actor: admin
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product refuses to add it
  kind: condition
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
---

# The folder cannot be added

## Trigger

An admin enters a folder that is not valid or is already a library.

## Outcome

No library is added.
