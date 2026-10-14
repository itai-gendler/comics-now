---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens the Metadata tab of a comic
  kind: actor
  actor: admin
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Volume
    - Year
    - Creators
    - Summary
  contexts:
    web:
      place: web::library::comic-details
- text: The Admin changes the series and issue number and saves
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::library::comic-details
- text: The Product saves the metadata and marks the comic Successful because it is complete
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
    from: Failed
    to: Successful
    facts:
    - Series
    - Issue number
  contexts:
    web:
      place: web::library::comic-details
- text: The Product writes the ComicInfo where the server keeps metadata
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Metadata storage
  contexts:
    web:
      place: web::library::comic-details
---

# Edit and save a comic's metadata

## Trigger

An admin finds a comic with wrong or missing metadata.

## Outcome

The comic carries the new metadata, and is Successful when it has a series, a publisher, a date and an issue number.

## Decision points

### Where is the metadata written?

Is the metadata storage the archive, a sidecar, or the database?

- Archive → ComicInfo.xml is written inside the CBZ, while a CBR keeps it in the database only
- Sidecar → a .ComicInfo.xml file is written beside the comic
- Database → nothing is written beside or inside the comic

## Edge cases

- Saving without a series, publisher, date or issue number leaves the comic Failed.
