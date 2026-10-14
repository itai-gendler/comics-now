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
- text: Continuous mode is on for the comic
  kind: condition
  actor: user
  entities:
  - entity: reading-preference
    effect: reads
    facts:
    - Continuous mode
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reader
- text: The User scrolls down the pages
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Page count
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

# Read as one continuous scroll

## Trigger

A person reads a comic whose continuous mode is on.

## Outcome

All pages scroll as one strip and progress follows the scroll.
