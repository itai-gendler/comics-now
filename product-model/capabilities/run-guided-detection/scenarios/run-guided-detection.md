---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Run Now on Guided Reader
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product queues every pending and failed comic
  kind: product
  actor: admin
  entities:
  - entity: guided-detection-run
    effect: creates
    to: Running
    facts:
    - Scope
    - Re-run completed
    - Queue
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product detects the panels of each comic in turn
  kind: product
  actor: admin
  entities:
  - entity: guided-view
    effect: changes
    from: Pending
    to: Processing
    facts: []
  - entity: guided-detection-run
    effect: changes
    facts:
    - Current comic
    - Queue
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product keeps each panel map
  kind: product
  actor: admin
  entities:
  - entity: guided-view
    effect: changes
    from: Processing
    to: Completed
    facts:
    - Panels
    - Source
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product ends the run when the queue is empty
  kind: product
  actor: admin
  entities:
  - entity: guided-detection-run
    effect: changes
    from: Running
    to: Finished
    facts:
    - Queue
  contexts:
    web:
      place: web::administration::guided-reader
---

# Run detection on everything pending

## Trigger

An admin wants Guided Views for the whole collection.

## Outcome

Every pending or failed comic has a Guided View or a recorded failure.
