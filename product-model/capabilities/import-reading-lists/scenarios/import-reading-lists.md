---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Import and picks a reading-list file
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::reading-lists
- text: The Product creates a reading list for each list in the file with the comics this server has
  kind: product
  actor: user
  entities:
  - entity: reading-list
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

# Import lists from a file

## Trigger

A person has a reading-list file.

## Outcome

The person has a new reading list for each list in the file.

## Edge cases

- Comics the server does not have are left out of the imported list.
- A list in the file that cannot be created is reported as skipped and the rest are imported.
