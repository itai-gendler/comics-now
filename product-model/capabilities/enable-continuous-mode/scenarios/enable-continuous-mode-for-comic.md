---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Enable Continuous Mode on a comic
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
- text: The Product records Continuous Mode as on for that comic and that person
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: creates
    facts:
    - Level
    - Target
    - Continuous mode
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comic-details
---

# Turn on Continuous Mode for one comic

## Trigger

A person wants one comic to read as one continuous scroll.

## Outcome

That comic opens as one continuous scroll for that person.
