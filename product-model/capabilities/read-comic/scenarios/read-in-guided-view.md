---
kind: alternative
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
- text: The Guided View of the comic is completed
  kind: condition
  actor: user
  entities:
  - entity: guided-view
    effect: reads
    facts:
    - Panels
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reader
- text: The Product steps through the panels in reading order
  kind: product
  actor: user
  entities:
  - entity: guided-view
    effect: reads
    facts:
    - Panels
  contexts:
    web:
      place: web::library::reader
- text: The Product saves the page reached for the person and for this device
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

# Read panel by panel

## Trigger

A person switches the reader to Guided View on a comic whose Guided View is ready.

## Outcome

The person reads the comic one panel, or one speech bubble, at a time.

## Edge cases

- Bubble Zoom steps through speech bubbles instead of panels.
