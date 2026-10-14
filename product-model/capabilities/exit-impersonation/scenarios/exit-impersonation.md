---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Exit Impersonation
  kind: actor
  actor: admin
  entities:
  - entity: impersonation
    effect: reads
    facts:
    - Started
  contexts:
    web:
      place: web::library
- text: The Product ends the impersonation and reloads the app as the admin
  kind: product
  actor: admin
  entities:
  - entity: impersonation
    effect: changes
    from: Active
    to: Ended
    facts: []
  contexts:
    web:
      place: web::library
---

# Return to your own view

## Trigger

An admin has finished checking a user's view.

## Outcome

The admin sees their own library again.
