---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Full Scan
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product re-reads every file in every library and the Smart Inbox
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Cover
    - Page count
  - entity: library
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::general-settings
---

# Run a full scan

## Trigger

An admin wants every file re-read, changed or not.

## Outcome

Every comic's metadata, cover and page count are refreshed.

## Edge cases

- A full scan goes ahead even while tagging is running.
