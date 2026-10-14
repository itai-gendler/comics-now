---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Edit, drags their reading lists into order and chooses Save Order
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
    - Position
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product saves the position of each reading list
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: changes
    facts:
    - Position
  contexts:
    web:
      place: web::library::reading-lists
---

# Order your lists

## Trigger

A person wants their current event at the top.

## Outcome

The lists appear in the new order.
