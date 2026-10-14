---
kind: edge
routes:
  web: Web
steps:
- text: The User chooses Download for Offline on a comic
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::library::series
- text: The Product cannot finish downloading the comic
  kind: condition
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::downloads
- text: The Product marks it failed in the queue
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: changes
    from: Queued
    to: Failed
    facts:
    - Progress
  contexts:
    web:
      place: web::library::downloads
---

# A download fails

## Trigger

The connection or the server stops a download for good.

## Outcome

The comic shows as failed in the queue and can be retried.
