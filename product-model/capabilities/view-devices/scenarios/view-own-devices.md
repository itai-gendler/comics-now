---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Devices
  kind: actor
  actor: user
  entities:
  - entity: device
    effect: reads
    facts:
    - Name
    - Browser
    - Registered
    - Last seen
  contexts:
    web:
      place: web::library::devices
---

# See your devices

## Trigger

A person opens Settings → Devices.

## Outcome

The person sees their devices, most recently seen first.
