---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Mark as Unread on a comic
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::library::series
- text: The Product sets the person's progress on the comic back to the first page
  kind: product
  actor: user
  entities:
  - entity: reading-progress
    effect: changes
    facts:
    - Last read page
    - Updated
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::series
---

# Mark one comic unread

## Trigger

A person wants to read a comic again from the start.

## Outcome

The comic shows as unread for that person.
