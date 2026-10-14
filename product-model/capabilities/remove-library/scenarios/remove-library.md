---
kind: primary
routes:
  web: Web
steps:
- text: The Admin removes a library
  kind: actor
  actor: admin
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product removes the library and its comics with their thumbnails and Guided Views
  kind: product
  actor: admin
  entities:
  - entity: library
    effect: removes
  - entity: comic
    effect: removes
    from: Successful
    with: library
  - entity: guided-view
    effect: removes
    from: Completed
    with: comic
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product removes the access grants that named the library or its folders
  kind: product
  actor: admin
  entities:
  - entity: access-grant
    effect: removes
  - entity: library
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::general-settings
---

# Remove a library

## Trigger

An admin no longer serves a folder.

## Outcome

The library and its comics are gone from the server; the files remain on disk.

## Edge cases

- Comics that are under no library and not in the Smart Inbox are cleared out at the same time.
