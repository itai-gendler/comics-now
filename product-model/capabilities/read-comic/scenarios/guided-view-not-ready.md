---
kind: edge
routes:
  web: Web
steps:
- text: The User turns on Guided View in the reader
  kind: actor
  actor: user
  entities:
  - entity: guided-view
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reader
- text: The comic has no completed Guided View
  kind: condition
  actor: user
  entities:
  - entity: guided-view
    effect: reads
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reader
---

# Guided View is not ready

## Trigger

A person asks for Guided View on a comic that has none yet.

## Outcome

The person keeps reading page by page.
