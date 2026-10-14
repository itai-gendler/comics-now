---
kind: primary
routes:
  web: Web
steps:
- text: The User opens a library card
  kind: actor
  actor: user
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
    - Organization
  contexts:
    web:
      place: web::library::libraries
- text: The Product lists the publishers in the library that the person may read
  kind: product
  actor: user
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  - entity: comic
    effect: reads
    facts:
    - Publisher
  - entity: access-grant
    effect: reads
    facts:
    - Level
    - Target
    - Includes everything below
  contexts:
    web:
      place: web::library::library
- text: The User opens a publisher and sees its series
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Publisher
    - Series
  contexts:
    web:
      place: web::library::publisher
- text: The User opens a series and sees its issues with their read badges
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Series
    - Issue number
    - Title
    - Year
    - Cover
  - entity: reading-progress
    effect: reads
    facts:
    - Last read page
    - Page count
  contexts:
    web:
      place: web::library::series
---

# Browse a library by publisher and series

## Trigger

A person wants to find a comic in a metadata library.

## Outcome

The person sees the issues of the series they chose, with covers, read badges and Guided View status.

## Edge cases

- A person with no access grants sees no libraries.
- Comics without a publisher or series are filed under Unknown Publisher and Unknown Series.
