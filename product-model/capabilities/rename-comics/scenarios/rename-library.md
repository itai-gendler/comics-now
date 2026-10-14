---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Rename Library, picks a library and types i want to do this
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
- text: The Product renames each Successful comic in the library by the naming rules
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Naming rules
  - entity: comic
    effect: changes
    facts:
    - File name
  - entity: library
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::management
---

# Rename a whole library

## Trigger

An admin has changed the naming rules and wants a library to follow them.

## Outcome

Every successfully tagged comic in the library is named by the rules.
