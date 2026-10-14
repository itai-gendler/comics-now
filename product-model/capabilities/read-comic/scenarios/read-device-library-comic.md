---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a file from a device library
  kind: actor
  actor: user
  entities:
  - entity: device-library
    effect: reads
    facts:
    - Folder name
    - Comics found
  contexts:
    web:
      place: web::library::libraries
- text: The Product opens the file in the browser and shows its pages
  kind: product
  actor: user
  entities:
  - entity: device-library
    effect: reads
    facts:
    - Comics found
  contexts:
    web:
      place: web::library::reader
---

# Read a comic from a device library

## Trigger

A person opens a comic in one of this browser's device libraries.

## Outcome

The person reads the file without it being uploaded to the server.
