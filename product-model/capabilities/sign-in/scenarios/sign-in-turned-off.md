---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin opens the server
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::library
- text: Sign-in is off
  kind: condition
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Sign-in
  contexts:
    web:
      place: web::library
- text: The Product treats the Admin as the built-in account
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: changes
    facts:
    - Last seen
  contexts:
    web:
      place: web::library
---

# Use the server with sign-in off

## Trigger

The server runs without Cloudflare Access sign-in configured.

## Outcome

Everyone who reaches the server uses the built-in admin account.
