---
kind: validation
routes:
  web: Web
steps:
- text: The User chooses a folder on their phone, tablet or computer
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::libraries
- text: The Product finds no CBZ or CBR files and says so
  kind: condition
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::libraries
---

# The chosen folder has no comics

## Trigger

A person picks a folder with no CBZ or CBR files.

## Outcome

Nothing is added.
