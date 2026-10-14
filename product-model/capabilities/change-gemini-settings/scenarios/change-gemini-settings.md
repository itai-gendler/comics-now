---
kind: primary
routes:
  web: Web
steps:
- text: The Admin accepts the Gemini compliance agreement
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::gemini
- text: The Product records the agreement
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Gemini agreement
  contexts:
    web:
      place: web::administration::gemini
- text: The Admin enters the API key, picks a model, turns cover matching on and saves
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Gemini model
    - Gemini cover matching
    - Gemini daily cap
    - Gemini requests today
  contexts:
    web:
      place: web::administration::gemini
- text: The Product saves the Gemini settings
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: changes
    facts:
    - Gemini API key
    - Gemini model
    - Gemini cover matching
    - Gemini daily cap
  contexts:
    web:
      place: web::administration::gemini
---

# Turn on Gemini cover matching

## Trigger

An admin wants covers compared by Gemini when tagging.

## Outcome

Tagging scans compare covers with Gemini until the daily cap is reached.
