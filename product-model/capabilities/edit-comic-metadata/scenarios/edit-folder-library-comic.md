---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin changes a comic's summary and saves
  kind: actor
  actor: admin
  entities:
  - entity: comic
    effect: reads
    facts:
    - Summary
  contexts:
    web:
      place: web::library::comic-details
- text: The comic's library is organized by folder
  kind: condition
  actor: admin
  entities:
  - entity: library
    effect: reads
    facts:
    - Organization
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comic-details
- text: The Product saves the metadata without writing it into or beside the file
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
    facts:
    - Summary
  contexts:
    web:
      place: web::library::comic-details
---

# Edit a comic in a folder library

## Trigger

An admin edits a comic in a library organized by folder.

## Outcome

The metadata is saved in the database only; the file on disk is left as it is.
