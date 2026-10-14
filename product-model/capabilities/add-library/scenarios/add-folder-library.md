---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin enters a folder, picks Folder Mode and chooses Add
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product adds the library
  kind: product
  actor: admin
  entities:
  - entity: library
    effect: creates
    facts:
    - Folder
    - Organization
  contexts:
    web:
      place: web::administration::general-settings
---

# Add a library organized by folder

## Trigger

An admin has an unsorted collection whose folders already make sense.

## Outcome

The folder is a library browsed by its own folders.
