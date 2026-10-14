---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the reader
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Page count
  contexts:
    web:
      place: web::library::comic-details
- text: The Product opens the comic at the page the person last reached
  kind: product
  actor: user
  entities:
  - entity: reading-progress
    effect: reads
    facts:
    - Last read page
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reader
- text: The User turns the pages
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
    - Page count
    - Updated
  - entity: device
    effect: changes
    facts:
    - Reading positions
    - Last seen
  contexts:
    web:
      place: web::library::reader
---

# Read page by page

## Trigger

A person opens the reader on a comic.

## Outcome

The person's progress and this device's position show the page they reached.

## Edge cases

- Reaching the last page completes the comic.
- At the end of a comic the reader offers the next comic in the series, or in the reading list it was opened from.
- A comic the person may not read does not open.
