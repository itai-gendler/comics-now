---
kind: alternative
routes:
  web: Web
steps:
- text: The User changes one library's defaults and saves
  kind: actor
  actor: user
  entities:
  - entity: reading-preference
    effect: reads
    facts:
    - Target
    - Manga mode
    - Continuous mode
  - entity: library
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comics-defaults
- text: The Product records the library's defaults and clears the person's choices for comics, series and publishers in it
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    effect: changes
    facts:
    - Manga mode
    - Continuous mode
  - entity: library
    effect: reads
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comics-defaults
---

# Set defaults for one library

## Trigger

A person wants one library, such as a manga collection, to read differently.

## Outcome

That library's comics read that way for the person, since the more specific choices under it were cleared.
