---
kind: validation
routes:
  web: Web
steps:
- text: The Admin turns cover matching on without accepting the agreement and saves
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Gemini agreement
  contexts:
    web:
      place: web::administration::gemini
- text: The Product refuses and keeps cover matching off
  kind: condition
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::gemini
---

# The agreement comes first

## Trigger

An admin enters a key or turns matching on without accepting the agreement.

## Outcome

Cover matching stays off.
