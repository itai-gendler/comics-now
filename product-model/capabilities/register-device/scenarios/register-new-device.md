---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the app in a new browser
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library
- text: The Product registers the device to the person with a name like iPad Pro - Safari
  kind: product
  actor: user
  entities:
  - entity: device
    effect: creates
    facts:
    - Name
    - Browser
    - Registered
    - Last seen
  contexts:
    web:
      place: web::library
---

# A new device connects

## Trigger

A person opens Comics Now! in a browser for the first time.

## Outcome

The device is registered to the person and appears in their Devices.
