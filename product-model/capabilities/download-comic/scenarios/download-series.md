---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Download Series
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Series
  contexts:
    web:
      place: web::library::publisher
- text: The Product queues every issue not yet downloaded
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: creates
    to: Queued
    facts:
    - Progress
  contexts:
    web:
      place: web::library::downloads
---

# Download a series or reading list

## Trigger

A person wants every issue of a series, or every comic of a reading list, offline.

## Outcome

Each comic is queued and downloaded in turn.
