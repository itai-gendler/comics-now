---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin picks a user in Devices
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  - entity: device
    effect: reads
    facts: []
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::devices
- text: The Product lists that user's devices
  kind: product
  actor: admin
  entities:
  - entity: device
    effect: reads
    facts:
    - Name
    - Browser
    - Registered
    - Last seen
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::devices
---

# An admin sees a user's devices

## Trigger

An admin wants to know where a user reads.

## Outcome

The admin sees that user's devices.
