---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Disable Manga Mode on a comic
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
- text: The Product records Manga Mode as off for that comic and that person
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: changes
    facts:
    - Manga mode
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comic-details
---

# Turn off Manga Mode for one comic

## Trigger

A person no longer wants a comic to read right to left.

## Outcome

That comic opens the ordinary way for that person.
