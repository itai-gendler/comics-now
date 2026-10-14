---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Enable Manga Mode on a comic
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
- text: The Product records Manga Mode as on for that comic and that person
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: creates
    facts:
    - Level
    - Target
    - Manga mode
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comic-details
---

# Turn on Manga Mode for one comic

## Trigger

A person wants one comic to read right to left.

## Outcome

That comic opens right to left for that person.
