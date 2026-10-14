---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Login as on a user
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::users
- text: The Product starts the impersonation
  kind: product
  actor: admin
  entities:
  - entity: impersonation
    effect: creates
    to: Active
    facts:
    - Started
  contexts:
    web:
      place: web::administration::users
- text: The Product reloads the app as the user
  kind: product
  actor: admin
  entities:
  - entity: impersonation
    effect: reads
    facts:
    - Started
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library
---

# View the library as a user

## Trigger

An admin wants to check what a restricted user sees.

## Outcome

The admin sees the library exactly as the user does, under a banner naming the user.

## Edge cases

- Starting and stopping are both recorded with the admin, the user and the time.
- Viewing as a user lasts at most eight hours.
