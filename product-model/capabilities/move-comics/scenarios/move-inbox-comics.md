---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Move Comic and picks the destination library
  kind: actor
  actor: admin
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::management
- text: The Product moves each Successful comic into the folders its rules give and keeps its progress, lists and Guided View
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Folder rules
  - entity: comic
    effect: changes
    facts:
    - Location
  - entity: guided-view
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::management
- text: The Product scans the libraries again
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::management
---

# File the Smart Inbox into a library

## Trigger

Tagged comics are ready in the Smart Inbox.

## Outcome

Each successfully tagged comic sits in the chosen library under its publisher and series folders.

## Edge cases

- A comic whose file name already exists at the destination is reported and left in the Smart Inbox.
- Emptied folders in the Smart Inbox are removed.
