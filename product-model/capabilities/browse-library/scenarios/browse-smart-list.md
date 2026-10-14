---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a library and picks a smart list
  kind: actor
  actor: user
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  contexts:
    web:
      place: web::library::library
- text: The Product selects the comics added in the last 14 days
  kind: product
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Added
    - Publisher
  contexts:
    web:
      place: web::library::library
---

# Open a smart list

## Trigger

A person wants the comics added in the last 14 days, or only downloaded, guided, manga or non-manga comics.

## Outcome

The person sees just the comics that list selects.

## Edge cases

- In the Smart Inbox the two counters show how many comics were tagged successfully and how many failed.
