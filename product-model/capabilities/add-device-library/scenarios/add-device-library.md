---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses a folder on their phone, tablet or computer
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::libraries
- text: The Product finds the CBZ and CBR files in it and remembers the folder in this browser
  kind: product
  actor: user
  entities:
  - entity: device-library
    effect: creates
    facts:
    - Folder name
    - Comics found
  contexts:
    web:
      place: web::library::libraries
---

# Add a folder from this device

## Trigger

A person has comics on their device they want to read here.

## Outcome

The folder appears as a library card in this browser.
