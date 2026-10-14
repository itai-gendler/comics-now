---
kind: primary
routes:
  web: Web
steps:
- text: A library scan has added comics
  kind: condition
  unattended: true
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Guided auto-run
  - entity: library
    effect: reads
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product runs detection on just those comics
  kind: product
  entities:
  - entity: guided-detection-run
    effect: creates
    to: Running
    facts:
    - Scope
    - Re-run completed
    - Queue
  - entity: guided-view
    effect: changes
    from: Pending
    to: Completed
    facts:
    - Panels
    - Source
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::guided-reader
---

# Detect panels in newly added comics

## Trigger

A library scan has added comics while automatic processing is on.

## Outcome

The new comics get Guided Views; the older backlog is left for a manual run.
