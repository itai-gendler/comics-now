---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses to add a comic to a list
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::library::series
- text: The User names a new list
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::add-to-reading-list
- text: The Product creates the reading list holding the comic
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: creates
    facts:
    - Name
    - Comics
    - Position
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::add-to-reading-list
---

# Create a list while adding comics

## Trigger

A person adding comics to a list wants a new one for them.

## Outcome

The person has a new reading list holding the chosen comics.
