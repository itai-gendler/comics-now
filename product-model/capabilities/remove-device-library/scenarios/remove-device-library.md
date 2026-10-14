---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Remove on a device library card and confirms
  kind: actor
  actor: user
  entities:
  - entity: device-library
    effect: reads
    facts:
    - Folder name
  contexts:
    web:
      place: web::library::libraries
- text: The Product forgets the folder in this browser
  kind: product
  actor: user
  entities:
  - entity: device-library
    effect: removes
  contexts:
    web:
      place: web::library::libraries
---

# Remove a device library

## Trigger

A person no longer wants a device folder in their library.

## Outcome

The card is gone from this browser and the files on the device are untouched.
