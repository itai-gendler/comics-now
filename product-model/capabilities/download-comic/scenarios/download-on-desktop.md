---
kind: validation
routes:
  web: Web
steps:
- text: The User chooses to download a comic on a desktop computer
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::library::comic-details
- text: The Product explains downloads are only on phones and tablets
  kind: condition
  actor: user
  entities: []
  contexts:
    web:
      place: web::library::comic-details
---

# Downloads are refused on a desktop

## Trigger

A person on a desktop computer tries to download a comic.

## Outcome

Nothing is queued.
