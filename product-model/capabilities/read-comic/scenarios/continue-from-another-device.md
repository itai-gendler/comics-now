---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens the reader
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::reader
- text: Another of the person's devices reached a page more recently
  kind: condition
  actor: user
  entities:
  - entity: device
    effect: reads
    facts:
    - Name
    - Reading positions
  contexts:
    web:
      place: web::library::reader
- text: The User chooses to continue from that device
  kind: actor
  actor: user
  entities:
  - entity: device
    effect: reads
    facts:
    - Name
    - Reading positions
  contexts:
    web:
      place: web::library::reader
- text: The Product jumps to that page and saves it for this device
  kind: product
  actor: user
  entities:
  - entity: reading-progress
    effect: changes
    facts:
    - Last read page
    - Updated
  - entity: device
    effect: changes
    facts:
    - Reading positions
  contexts:
    web:
      place: web::library::reader
---

# Continue where another device left off

## Trigger

A person opens a comic that another of their devices has read further since this one last did.

## Outcome

The reader jumps to the other device's page.

## Edge cases

- Ignoring the offer stops it reappearing for that same position; a newer position from any device offers again.
