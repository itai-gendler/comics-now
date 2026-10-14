---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Set to Manga Mode on a series
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
- text: The Product records Manga Mode as on at that level for that person
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: creates
    facts:
    - Level
    - Target
    - Manga mode
  contexts:
    web:
      place: web::library::publisher
---

# Turn on Manga Mode for a series, publisher or library

## Trigger

A person wants everything in a series, publisher or library to read right to left.

## Outcome

Every comic under it opens right to left unless a more specific choice says otherwise.
