---
kind: primary
routes:
  web: Web
steps:
- text: The User removes a device in Devices
  kind: actor
  actor: user
  entities:
  - entity: device
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::library::devices
- text: The Product deletes the device with its reading positions
  kind: product
  actor: user
  entities:
  - entity: device
    effect: removes
  contexts:
    web:
      place: web::library::devices
---

# Remove one of your devices

## Trigger

A person no longer uses a tablet.

## Outcome

The device and its reading positions are gone; the person's progress stays.
