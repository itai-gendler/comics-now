---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Cancel Current
  kind: actor
  actor: admin
  entities:
  - entity: guided-detection-run
    effect: reads
    facts:
    - Current comic
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product stops working on that comic and continues with the queue
  kind: product
  actor: admin
  entities:
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
---

# Skip the current comic

## Trigger

One comic is taking too long.

## Outcome

The run moves on to the next comic.
