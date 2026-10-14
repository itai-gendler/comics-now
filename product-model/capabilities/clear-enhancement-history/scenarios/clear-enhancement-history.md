---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Clear Enhancement History
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::tagging-settings
- text: The Product forgets what tagging has handled and returns every comic to Pending
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
    from: Successful
    to: Pending
    facts: []
  contexts:
    web:
      place: web::administration::tagging-settings
---

# Clear the history

## Trigger

An admin wants tagging to start afresh.

## Outcome

Every comic is Pending and the next tagging scan considers them all.
