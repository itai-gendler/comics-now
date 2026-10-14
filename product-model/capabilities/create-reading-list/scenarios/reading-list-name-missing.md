---
kind: validation
routes:
  web: Web
steps:
- text: The User creates a list without a name
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product refuses because a list name is required
  kind: condition
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::reading-lists
---

# A list needs a name

## Trigger

A person tries to create a list with no name.

## Outcome

No list is created.
