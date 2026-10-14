---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses to add a series to a list
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Series
  contexts:
    web:
      place: web::library::publisher
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
- text: The Product appends every issue of the series to the reading list
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: changes
    facts:
    - Comics
  contexts:
    web:
      place: web::library::add-to-reading-list
---

# Add a whole series to a list

## Trigger

A person wants every issue of a series on a list.

## Outcome

All the series' issues follow the list's existing comics.
