---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin enters a new service port and saves
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Tagger service port
  contexts:
    web:
      place: web::administration::tagging-settings
- text: The Product saves the port and restarts the tagging service on it
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Tagger service port
  contexts:
    web:
      place: web::administration::tagging-settings
---

# Move the tagging service to another port

## Trigger

The tagging service's port is taken.

## Outcome

The tagging service runs on the new port.

## Edge cases

- A port outside 1 to 65535 is refused.
- If the service fails to restart the port is still saved and a warning is shown.
