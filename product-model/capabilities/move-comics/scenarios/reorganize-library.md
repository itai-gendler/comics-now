---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Reorganize Library, picks a library and types i want to do this
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
- text: The Product moves each Successful comic in the library into its folders
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Folder rules
  - entity: comic
    effect: changes
    facts:
    - Location
  - entity: library
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::management
---

# Reorganize a whole library

## Trigger

An admin has changed the folder rules.

## Outcome

Every successfully tagged comic in the library sits in the folders the rules give.
