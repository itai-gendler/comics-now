---
kind: primary
routes:
  web: Web
steps:
- text: The User sees how much space downloads take and chooses Clear All Downloaded Comics
  kind: actor
  actor: user
  entities:
  - entity: downloaded-comic
    effect: reads
    facts:
    - Size
  contexts:
    web:
      place: web::library::offline-data
- text: The Product removes every downloaded comic from this browser
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: removes
    from: Downloaded
  contexts:
    web:
      place: web::library::offline-data
---

# Clear all downloads

## Trigger

A person needs space back on their phone.

## Outcome

No comics are kept in this browser; they must be downloaded again to read offline.
