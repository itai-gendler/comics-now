---
kind: validation
routes:
  web: Web
steps:
- text: The User opens the app with a device id registered to another person
  kind: actor
  actor: user
  entities:
  - entity: device
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library
- text: The Product refuses to register the device to them
  kind: condition
  actor: user
  entities:
  - entity: device
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library
---

# A device registered to someone else

## Trigger

A browser presents a device id another person has registered.

## Outcome

The device is not registered to this person.
