---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens the app in a browser they used before
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library
- text: The Product recognizes the browser as one of the person's devices and keeps its name
  kind: product
  actor: user
  entities:
  - entity: device
    effect: changes
    facts:
    - Last seen
  contexts:
    web:
      place: web::library
---

# A known browser connects again

## Trigger

A browser the person used before reconnects after losing its stored id.

## Outcome

The browser keeps its earlier registration and name.
