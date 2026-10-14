---
kind: alternative
routes:
  web: Web
steps:
- text: The User marks the reading list as read
  kind: actor
  actor: user
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
    - Comics
  contexts:
    web:
      place: web::library::reading-list
- text: The Product sets the person's progress on every comic of the list to its last page
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
      place: web::library::reading-list
---

# Mark a reading list read

## Trigger

A person has read everything on one of their reading lists.

## Outcome

Every comic on the list shows as read for that person.
