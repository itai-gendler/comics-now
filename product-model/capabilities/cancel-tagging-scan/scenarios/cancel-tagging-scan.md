---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Cancel on the tagging console
  kind: actor
  actor: admin
  entities:
  - entity: tagging-scan
    effect: reads
    facts:
    - Mode
    - Output
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product stops the scan
  kind: product
  actor: admin
  entities:
  - entity: tagging-scan
    effect: changes
    from: Running
    to: Cancelled
    facts:
    - Output
  contexts:
    web:
      place: web::administration::tag-comics-now
---

# Stop the scan

## Trigger

An admin needs the tagging scan to stop.

## Outcome

The scan stops before the next comic.

## Edge cases

- A comic waiting for review when the scan stops can still be applied or skipped.
