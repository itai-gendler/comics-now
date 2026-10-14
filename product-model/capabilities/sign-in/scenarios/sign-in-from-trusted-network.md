---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin opens the server directly from a trusted network address
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::library
- text: The Product reads the trusted networks
  kind: condition
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Trusted networks
  contexts:
    web:
      place: web::library
- text: The Product signs the Admin in as the built-in account
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

# Arrive from a trusted network

## Trigger

Someone opens the server directly from an address on the trusted network list, with no Cloudflare Access identity.

## Outcome

They use the built-in admin account.

## Edge cases

- A request that came through a proxy or tunnel never counts as coming from a trusted network.
- A request that carries a Cloudflare Access identity uses that identity even from a trusted network.
