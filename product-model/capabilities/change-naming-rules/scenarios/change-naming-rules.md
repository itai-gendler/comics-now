---
kind: primary
routes:
  web: Web
steps:
- text: The Admin arranges the name tokens, checks the preview and chooses Save Naming Rules
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Naming rules
  contexts:
    web:
      place: web::administration::management
- text: The Product saves the naming rules
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Naming rules
  contexts:
    web:
      place: web::administration::management
---

# Save naming rules

## Trigger

An admin wants file names like Series #001 (Year).

## Outcome

Later renames use the new rules.
