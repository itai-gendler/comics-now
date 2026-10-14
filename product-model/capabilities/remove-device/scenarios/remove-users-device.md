---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin picks a user and removes one of their devices
  kind: actor
  actor: admin
  entities:
  - entity: device
    effect: reads
    facts:
    - Name
  - entity: account
    effect: reads
    facts:
    - Email
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::devices
- text: The Product deletes the device
  kind: product
  actor: admin
  entities:
  - entity: device
    effect: removes
  contexts:
    web:
      place: web::library::devices
---

# An admin removes a user's device

## Trigger

An admin cleans up a user's old devices.

## Outcome

The user's device is gone.
