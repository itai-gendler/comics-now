---
kind: validation
routes:
  web: Web
steps:
- text: The Admin enters a scan interval of 2000 minutes and saves
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Scan interval
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product refuses because the interval must be 1 to 1440 minutes
  kind: condition
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
---

# The scan interval is out of range

## Trigger

An admin enters an interval below 1 or above 1440 minutes.

## Outcome

Nothing is saved.
