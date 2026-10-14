---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a folder library card
  kind: actor
  actor: user
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
    - Organization
  contexts:
    web:
      place: web::library::libraries
- text: The Product lists the folders and comics in it that the person may read
  kind: product
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - File name
    - Cover
  - entity: access-grant
    effect: reads
    facts:
    - Level
    - Target
    - Includes everything below
  contexts:
    web:
      place: web::library::folder
- text: The User opens a sub-folder and sees its comic files and read badges
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - File name
    - Cover
  - entity: reading-progress
    effect: reads
    facts:
    - Last read page
  contexts:
    web:
      place: web::library::folder
---

# Browse a library by its folders

## Trigger

A person opens a library organized by folder.

## Outcome

The person sees the folders and comic files of the folder they opened.

## Edge cases

- A comic file not scanned yet is listed by file name without a cover until the next scan.
