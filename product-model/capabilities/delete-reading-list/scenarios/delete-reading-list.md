---
kind: primary
routes:
  web: Web
steps:
- text: The User deletes the reading list
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product removes the reading list
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: removes
  contexts:
    web:
      place: web::library::reading-lists
---

# Delete a list

## Trigger

A person no longer wants a list.

## Outcome

The list is gone from the person's reading lists; other people's copies stay.
