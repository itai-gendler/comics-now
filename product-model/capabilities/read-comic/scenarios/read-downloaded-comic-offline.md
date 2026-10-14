---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a downloaded comic while offline
  kind: actor
  actor: user
  entities:
  - entity: downloaded-comic
    effect: reads
    facts:
    - Pages
  contexts:
    web:
      place: web::library::reader
- text: The Product shows its pages from the copy in this browser
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: reads
    facts:
    - Pages
  contexts:
    web:
      place: web::library::reader
---

# Read a downloaded comic offline

## Trigger

A person without a connection opens a comic downloaded in this browser.

## Outcome

The person reads it from the browser's copy.

## Edge cases

- Changes that need the server, such as editing reading lists, are unavailable offline.
