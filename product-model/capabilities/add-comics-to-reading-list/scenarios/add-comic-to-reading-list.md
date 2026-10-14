---
kind: primary
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
      place: web::library::comic-details
- text: The User picks the reading list and saves
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::library::add-to-reading-list
- text: The Product appends the comic to the reading list
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: changes
    facts:
    - Comics
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::add-to-reading-list
---

# Add a comic to a list

## Trigger

A person wants a comic on a list.

## Outcome

The comic is the last on the list.

## Edge cases

- A comic already on the list keeps its place.
- Reading lists cannot be changed while offline.
