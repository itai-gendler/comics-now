---
kind: alternative
routes:
  web: Web
steps:
- text: The User arrives with their Cloudflare Access identity
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library
- text: The Product records when the person was last seen
  kind: product
  actor: user
  entities:
  - entity: account
    effect: changes
    facts:
    - Last seen
  contexts:
    web:
      place: web::library
- text: The User sees the libraries their access grants open
  kind: condition
  actor: user
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
  - entity: access-grant
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::libraries
---

# Come back signed in

## Trigger

A person who has used the server before opens it again.

## Outcome

The person sees their own library, and their account shows when they were last seen.
