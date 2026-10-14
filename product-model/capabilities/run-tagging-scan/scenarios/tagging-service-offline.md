---
kind: edge
routes:
  web: Web
steps:
- text: The Admin chooses Run on the tagging console
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The tagging service does not answer
  kind: condition
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Tagger service port
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product reports the engine is offline
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::tag-comics-now
---

# The tagging service is unreachable

## Trigger

The tagging service does not answer and cannot be started.

## Outcome

Nothing is tagged and the console says the engine is offline.
