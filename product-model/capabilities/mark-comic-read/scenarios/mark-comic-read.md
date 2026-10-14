---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Mark as Read on a comic
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
- text: The Product sets the person's progress on the comic to its last page
  kind: product
  actor: user
  entities:
  - entity: reading-progress
    effect: changes
    facts:
    - Last read page
    - Page count
    - Updated
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::series
---

# Mark one comic read

## Trigger

A person has read a comic elsewhere.

## Outcome

The comic shows as read for that person.
