---
kind: primary
routes:
  web: Web
steps:
- text: The Guided Reader schedule has elapsed
  kind: condition
  unattended: true
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Guided schedule
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product runs detection on every pending and failed comic
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

# Detect panels on a schedule

## Trigger

The Guided Reader schedule comes round.

## Outcome

Pending and failed comics are processed.
