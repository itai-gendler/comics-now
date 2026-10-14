---
kind: edge
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
- text: The panel detector fails on a comic
  kind: condition
  actor: admin
  entities:
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product records the failure and moves on
  kind: product
  actor: admin
  entities:
  - entity: guided-view
    effect: changes
    from: Processing
    to: Failed
    facts:
    - Error
  contexts:
    web:
      place: web::administration::guided-reader
---

# Detection fails on a comic

## Trigger

The panel detector cannot process a comic.

## Outcome

The comic's Guided View is Failed with the reason, and the run goes on.
