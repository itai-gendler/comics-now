---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Rename on the Operations tab
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::management
- text: The Product renames each Successful comic in the Smart Inbox by the naming rules
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Naming rules
  - entity: comic
    effect: changes
    facts:
    - File name
  contexts:
    web:
      place: web::administration::management
---

# Rename the Smart Inbox

## Trigger

Tagging has finished on the Smart Inbox.

## Outcome

Each successfully tagged comic there is named by the naming rules.

## Edge cases

- A comic without metadata is reported as an error and left alone.
