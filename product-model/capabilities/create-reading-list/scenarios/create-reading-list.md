---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses New List and gives it a name and description
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product creates the reading list for that person
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: creates
    facts:
    - Name
    - Description
    - Comics
    - Position
  contexts:
    web:
      place: web::library::reading-lists
---

# Create a new list

## Trigger

A person wants a new reading order.

## Outcome

The person has a new, empty reading list.
