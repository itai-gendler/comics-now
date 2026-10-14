---
kind: primary
routes:
  web: Web
steps:
- text: The Admin lowers the auto-accept confidence, enables Metron with its sign-in and chooses Save Settings
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Auto-accept confidence
    - Review confidence
    - Enabled sources
    - Source credentials
  contexts:
    web:
      place: web::administration::tagging-settings
- text: The Product saves the settings and reschedules tagging
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Auto-accept confidence
    - Enabled sources
    - Source credentials
  contexts:
    web:
      place: web::administration::tagging-settings
---

# Save tagging settings

## Trigger

An admin wants fewer comics sent to review.

## Outcome

Later tagging scans use the new settings.

## Edge cases

- A blank Metron password keeps the saved one.
