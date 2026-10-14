---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Logout and confirms
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library
- text: The Product clears the comics downloaded in this browser
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: removes
    from: Downloaded
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library
- text: The Product sends the person to Cloudflare Access to sign out
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::library
---

# Log out

## Trigger

A person chooses to log out and confirms.

## Outcome

The browser keeps none of the person's data and they are signed out of Cloudflare Access.

## Edge cases

- Choosing not to confirm keeps the person signed in and their downloads in place.
