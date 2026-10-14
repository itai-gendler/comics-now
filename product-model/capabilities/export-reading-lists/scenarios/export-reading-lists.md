---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Export All Lists
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product produces a file of every reading list of the person with its comics in order
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
    - Description
    - Comics
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reading-lists
---

# Export all lists

## Trigger

A person wants a backup of their lists or to share them.

## Outcome

The person has a JSON file of their lists.
