---
kind: primary
routes:
  web: Web
steps:
- text: The User changes the name and description of the reading list and saves
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
    - Description
  contexts:
    web:
      place: web::library::reading-list
- text: The Product saves the reading list
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: changes
    facts:
    - Name
    - Description
  contexts:
    web:
      place: web::library::reading-list
---

# Rename a list

## Trigger

A person wants a better name for a list.

## Outcome

The list has the new name and description.

## Edge cases

- An empty name is refused.
