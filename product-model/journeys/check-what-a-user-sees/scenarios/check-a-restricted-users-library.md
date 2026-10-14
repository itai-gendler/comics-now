---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Admin chooses Login as on the user
  kind: actor
  actor: admin
  capability: log-in-as-user
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
- text: The Product starts the impersonation and reloads the app as the user
  kind: product
  actor: admin
  capability: log-in-as-user
  entities:
  - entity: impersonation
    effect: creates
    to: Active
    facts:
    - Started
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library
- text: The Admin opens a library card and sees only the publishers the user may read
  kind: actor
  actor: admin
  capability: browse-library
  entities:
  - entity: library
    effect: reads
    facts:
    - Folder
    - Organization
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::libraries
- text: The Admin chooses Exit Impersonation
  kind: actor
  actor: admin
  capability: exit-impersonation
  entities:
  - entity: impersonation
    effect: reads
    facts:
    - Started
  contexts:
    web:
      place: web::library
- text: The Product ends the impersonation and reloads the app as the admin
  kind: product
  actor: admin
  capability: exit-impersonation
  entities:
  - entity: impersonation
    effect: changes
    from: Active
    to: Ended
    facts: []
  contexts:
    web:
      place: web::library
---

# Check a restricted user's library

## Trigger

An admin has just set a user's permissions and wants to see the result.

## Outcome

The admin saw only the publishers the user may read, and is back in their own view.
