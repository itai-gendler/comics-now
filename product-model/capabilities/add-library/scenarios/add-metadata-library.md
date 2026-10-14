---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a folder, picks Metadata Mode and chooses Add
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

# Add a library organized by metadata

## Trigger

An admin has a curated collection to share.

## Outcome

The folder is a library whose comics are grouped by publisher and series after the next scan.
