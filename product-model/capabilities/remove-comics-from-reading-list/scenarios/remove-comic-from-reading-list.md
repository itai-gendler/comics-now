---
kind: primary
routes:
  web: Web
steps:
- text: The User removes a comic from the reading list
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
- text: The Product takes the comic off the reading list
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
      place: web::library::reading-list
---

# Remove a comic from a list

## Trigger

A person no longer wants a comic on a list.

## Outcome

The comic is no longer on the list.
