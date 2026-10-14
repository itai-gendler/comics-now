---
kind: primary
routes:
  web: Web
steps:
- text: The User turns Manga Mode on under the master defaults and saves
  kind: actor
  actor: user
  entities:
  - entity: reading-preference
    as: library-default
    effect: reads
    facts:
    - Manga mode
    - Continuous mode
  contexts:
    web:
      place: web::library::comics-defaults
- text: The Product clears the person's choices for single comics, series and publishers
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    as: override
    effect: removes
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comics-defaults
- text: The Product records the default for each library
  kind: product
  actor: user
  entities:
  - entity: reading-preference
    as: library-default
    effect: creates
    facts:
    - Level
    - Target
    - Manga mode
  - entity: library
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::comics-defaults
---

# Set defaults for every library

## Trigger

A person wants all their comics to read right to left, or as a continuous scroll.

## Outcome

Every comic reads that way for the person, since the more specific choices were cleared.
