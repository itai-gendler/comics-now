---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin searches ComicVine from the Metadata tab and picks an issue
  kind: actor
  actor: admin
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
  contexts:
    web:
      place: web::library::comic-details
- text: The Product fills the form from the issue's ComicVine details
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - ComicVine API key
  contexts:
    web:
      place: web::library::comic-details
- text: The Admin saves
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::library::comic-details
- text: The Product saves the metadata to the comic
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
    from: Pending
    to: Successful
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Volume
    - Year
    - Creators
    - Summary
  contexts:
    web:
      place: web::library::comic-details
---

# Fill metadata from ComicVine

## Trigger

An admin wants ComicVine's data for a comic.

## Outcome

The comic carries the issue's ComicVine metadata.
