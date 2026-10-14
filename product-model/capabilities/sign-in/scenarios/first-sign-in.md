---
kind: primary
routes:
  web: Web
steps:
- text: The User arrives with the identity Cloudflare Access signed them in with
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::library
- text: The Product creates an account for that email
  kind: product
  actor: user
  entities:
  - entity: account
    effect: creates
    facts:
    - Email
    - Built-in
    - Joined
    - Last seen
  contexts:
    web:
      place: web::library
- text: The Product gives the person a copy of each reading list the built-in account keeps
  kind: product
  actor: user
  entities:
  - entity: reading-list
    effect: creates
    facts:
    - Name
    - Description
    - Comics
    - Position
  - entity: account
    effect: reads
    facts: []
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

# Sign in for the first time

## Trigger

A person opens the server for the first time after Cloudflare Access has signed them in.

## Outcome

The person has an account and their own copies of the default reading lists, and sees the libraries open to them.

## Edge cases

- A request with no Cloudflare Access identity, or one Access did not sign for this server, is refused and nothing is shown.
- Someone whose email is the configured admin email arrives as the Admin.
