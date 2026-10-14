---
kind: primary
routes:
  web: Web
steps:
- text: The User drags the comics of the reading list into a new order and saves
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Comics
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reading-list
- text: The Product saves the order of the reading list
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: changes
    facts:
    - Comics
  contexts:
    web:
      place: web::library::reading-list
---

# Set a list's reading order

## Trigger

A person wants a crossover read in chronological order.

## Outcome

The list's comics are in the new order.
