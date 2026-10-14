---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Run Guided Detection on a series
  kind: actor
  actor: admin
  entities:
  - entity: comic
    effect: reads
    facts:
    - Series
  contexts:
    web:
      place: web::library::publisher
- text: The Product queues the series' comics that have no Guided View
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
  - entity: guided-view
    effect: reads
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::publisher
- text: The Product detects their panels
  kind: product
  actor: admin
  entities:
  - entity: guided-view
    effect: changes
    from: Pending
    to: Completed
    facts:
    - Panels
    - Source
  contexts:
    web:
      place: web::library::publisher
---

# Run detection on one series

## Trigger

An admin wants Guided Views for a series they are about to read.

## Outcome

The series' comics without a Guided View get one.

## Edge cases

- Force Re-run includes the comics that already have a Guided View.
- A run cannot start while another is in progress.
