---
kind: primary
routes:
  web: Web
steps:
- text: The Admin turns on automatic runs for new additions, sets a daily schedule and saves
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Guided auto-run
    - Guided schedule
  contexts:
    web:
      place: web::administration::guided-reader
- text: The Product saves the settings and schedules the next run
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Guided auto-run
    - Guided schedule
  contexts:
    web:
      place: web::administration::guided-reader
---

# Save automatic processing

## Trigger

An admin wants Guided Views made without starting runs by hand.

## Outcome

Detection follows the new settings.
