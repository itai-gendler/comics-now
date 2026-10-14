---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Unset Manga Mode on a series
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
- text: The Product records Manga Mode as off at that level for that person
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: changes
    facts:
    - Manga mode
  contexts:
    web:
      place: web::library::publisher
---

# Turn off Manga Mode for a series, publisher or library

## Trigger

A person no longer wants a series, publisher or library to read right to left.

## Outcome

Every comic under it opens the ordinary way unless a more specific choice says otherwise.
