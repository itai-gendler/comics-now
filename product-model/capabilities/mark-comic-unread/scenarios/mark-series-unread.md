---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Mark Series as Unread
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Series
  contexts:
    web:
      place: web::library::publisher
- text: The Product sets the person's progress on every issue back to the first page
  kind: product
  actor: user
  entities:
  - entity: reading-progress
    effect: changes
    facts:
    - Last read page
    - Updated
  contexts:
    web:
      place: web::library::publisher
---

# Mark a whole series unread

## Trigger

A person wants to re-read a series.

## Outcome

Every issue of the series shows as unread for that person.
