---
kind: primary
routes:
  web: Web
steps:
- text: The User picks a comic
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Cover
  contexts:
    web:
      place: web::library::series
- text: The User sees its cover, metadata and reading position
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Volume
    - Year
    - Creators
    - Summary
    - Cover
    - Page count
  - entity: reading-progress
    effect: reads
    facts:
    - Last read page
    - Page count
  contexts:
    web:
      place: web::library::comic-details
---

# Open a comic's details

## Trigger

A person picks a comic in a series, list or search.

## Outcome

The person sees the comic's details and can read it from where they left off.
