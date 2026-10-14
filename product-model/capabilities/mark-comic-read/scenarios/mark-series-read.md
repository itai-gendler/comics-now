---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Mark Series as Read
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
- text: The Product sets the person's progress on every issue of the series to its last page
  kind: product
  actor: user
  entities:
  - entity: reading-progress
    effect: changes
    facts:
    - Last read page
    - Page count
    - Updated
  contexts:
    web:
      place: web::library::publisher
---

# Mark a whole series read

## Trigger

A person has read every issue of a series.

## Outcome

Every issue of the series shows as read for that person.

## Edge cases

- Bulk Mark Read/Unread on a publisher or a library marks every comic under it the same way.
