---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Set to Continuous Mode on a series
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
- text: The Product records Continuous Mode as on at that level for that person
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: creates
    facts:
    - Level
    - Target
    - Continuous mode
  contexts:
    web:
      place: web::library::publisher
---

# Turn on Continuous Mode for a series, publisher or library

## Trigger

A person wants everything in a series, publisher or library to read as one continuous scroll.

## Outcome

Every comic under it opens as one continuous scroll unless a more specific choice says otherwise.
