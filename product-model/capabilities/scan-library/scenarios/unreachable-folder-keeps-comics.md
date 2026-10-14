---
kind: edge
routes:
  web: Web
steps:
- text: The Admin chooses Scan Now
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
- text: A library folder cannot be read
  kind: condition
  actor: admin
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product skips removing missing comics for the whole scan
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::general-settings
---

# A library folder cannot be reached

## Trigger

A library's folder is missing during a scan, for example an unmounted network share.

## Outcome

No comic is removed, so nobody loses progress or list entries.

## Edge cases

- A comic whose file still exists is never removed, even if the scan missed it.
