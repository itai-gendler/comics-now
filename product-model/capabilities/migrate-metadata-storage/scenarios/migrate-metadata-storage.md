---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses to migrate everything to sidecar storage
  kind: actor
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Metadata storage
  contexts:
    web:
      place: web::administration::tagging-settings
- text: The Product writes each comic's metadata to a sidecar file beside it
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - File name
  contexts:
    web:
      place: web::administration::tagging-settings
---

# Migrate to sidecar files

## Trigger

An admin switches storage to sidecars and wants existing comics to follow.

## Outcome

Every comic's metadata is in a sidecar file beside it.

## Edge cases

- Migrating to the archive writes into CBZ files only; CBR comics keep their metadata in the database.
- Migrating to the database removes sidecar files and writes nothing beside or into the comics.
