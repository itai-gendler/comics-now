---
kind: validation
routes:
  web: Web
steps:
- text: The Admin starts Reorganize Library without typing the phrase
  kind: actor
  actor: admin
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  contexts:
    web:
      place: web::administration::management
- text: The Product refuses until the phrase is typed
  kind: condition
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::management
---

# The confirmation phrase is missing

## Trigger

An admin starts a whole-library reorganization without the exact phrase.

## Outcome

Nothing moves.
