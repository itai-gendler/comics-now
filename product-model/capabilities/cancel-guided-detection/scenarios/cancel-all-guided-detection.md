---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Cancel All
  kind: actor
  actor: admin
  entities:
  - entity: guided-detection-run
    effect: reads
    facts:
    - Scope
    - Current comic
    - Queue
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product drops the queue and returns the current comic to pending
  kind: product
  actor: admin
  entities:
  - entity: guided-detection-run
    effect: changes
    from: Running
    to: Cancelled
    facts:
    - Queue
  - entity: guided-view
    effect: changes
    from: Processing
    to: Pending
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::guided-reader
---

# Cancel the whole run

## Trigger

An admin needs the server's resources back.

## Outcome

The run stops and the comic that was being processed returns to pending.
