---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Cancel on a queued comic
  kind: actor
  actor: user
  entities:
  - entity: downloaded-comic
    effect: reads
    facts:
    - Progress
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::downloads
- text: The Product removes it from the queue
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: removes
    from: Queued
  contexts:
    web:
      place: web::library::downloads
---

# Cancel a queued comic

## Trigger

A person changes their mind about a download.

## Outcome

The comic is out of the queue and nothing of it is kept.
