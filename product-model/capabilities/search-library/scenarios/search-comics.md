---
kind: primary
routes:
  web: Web
steps:
- text: The User types words to search for
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library
- text: The Product finds the comics they may read whose metadata matches
  kind: product
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
    - Publisher
    - Creators
    - Year
  - entity: access-grant
    effect: reads
    facts:
    - Level
    - Target
    - Includes everything below
  contexts:
    web:
      place: web::library::search-results
- text: The User filters the results to unread comics
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
    - Issue number
    - Cover
  - entity: reading-progress
    effect: reads
    facts:
    - Last read page
  contexts:
    web:
      place: web::library::search-results
---

# Search for comics

## Trigger

A person types a search.

## Outcome

The person sees the matching comics they may read.

## Edge cases

- An empty search returns nothing.
