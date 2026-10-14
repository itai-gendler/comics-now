---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Unset Continuous Mode on a series
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
- text: The Product records Continuous Mode as off at that level for that person
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: changes
    facts:
    - Continuous mode
  contexts:
    web:
      place: web::library::publisher
---

# Turn off Continuous Mode for a series, publisher or library

## Trigger

A person no longer wants a series, publisher or library to read as one continuous scroll.

## Outcome

Every comic under it opens the ordinary way unless a more specific choice says otherwise.
