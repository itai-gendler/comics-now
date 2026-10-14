---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses New List and names it
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::library::reading-lists
- text: The Admin is using the built-in account
  kind: condition
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Built-in
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product creates the reading list for the built-in account
  kind: product
  actor: admin
  entities:
  - entity: reading-list
    as: own
    effect: creates
    facts:
    - Name
    - Description
    - Comics
    - Position
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product gives every other person a copy with the same comics in the same order
  kind: product
  actor: admin
  entities:
  - entity: reading-list
    as: copy
    effect: creates
    facts:
    - Name
    - Description
    - Comics
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::reading-lists
---

# The built-in account creates a list

## Trigger

The built-in admin account, used on a trusted network or with sign-in off, creates a reading list.

## Outcome

Every user has their own copy of the list, and people who arrive later receive it too.
