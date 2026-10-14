---
kind: primary
routes:
  web: Web
steps:
- text: The Admin changes the scan interval and allowed formats and chooses Save Settings
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Scan interval
    - Allowed formats
    - Metadata storage
    - ComicVine API key
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product saves the settings and schedules the next scan
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Scan interval
    - Allowed formats
    - Metadata storage
    - ComicVine API key
  contexts:
    web:
      place: web::administration::general-settings
---

# Save general settings

## Trigger

An admin wants scans every hour and CBR comics included.

## Outcome

Scans follow the new interval and include the chosen formats.
