---
kind: primary
routes:
  web: Web
steps:
- text: The Admin adds a level, checks the preview and chooses Save Folder Rules
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Folder rules
  contexts:
    web:
      place: web::administration::management
- text: The Product saves the folder rules
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Folder rules
  contexts:
    web:
      place: web::administration::management
---

# Save folder rules

## Trigger

An admin wants comics filed as Publisher/Series (vVolume).

## Outcome

Later moves use the new levels.
