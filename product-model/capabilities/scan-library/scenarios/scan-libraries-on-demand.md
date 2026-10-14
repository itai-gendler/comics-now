---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Scan Now
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product reads the metadata inside each new file and adds the comic with its cover and page count
  kind: product
  actor: admin
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
    - Organization
  - entity: server-settings
    effect: reads
    facts:
    - Allowed formats
  - entity: comic
    as: new
    effect: creates
    to: Pending
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Volume
    - Year
    - Creators
    - Summary
    - Cover
    - Page count
    - File name
    - Location
    - Added
  - entity: guided-view
    as: new-view
    effect: creates
    to: Pending
    facts:
    - Panels
    with: new
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product removes the comics whose files are gone
  kind: product
  actor: admin
  entities:
  - entity: comic
    as: missing
    effect: removes
    from: Pending
  - entity: guided-view
    as: missing-view
    effect: removes
    from: Pending
    with: missing
  contexts:
    web:
      place: web::administration::general-settings
---

# Scan now

## Trigger

An admin has copied new comics into a library.

## Outcome

The new comics are in the library with covers and metadata.

## Edge cases

- Only folders changed since the last scan are read again.
- A comic whose metadata has a series, publisher, date and issue number is added as Successful.
- In a folder library the publisher and series come from the folders, not the file.
