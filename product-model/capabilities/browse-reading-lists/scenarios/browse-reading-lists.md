---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Reading Lists
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
    - Description
    - Position
    - Progress
  contexts:
    web:
      place: web::library::reading-lists
- text: The User opens a list
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
    - Comics
    - Progress
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
      place: web::library::reading-list
---

# See your reading lists

## Trigger

A person opens Reading Lists.

## Outcome

The person sees each of their lists with its progress, and the comics of the one they opened.

## Edge cases

- Filtering by a publisher keeps the lists holding at least one of its comics.
