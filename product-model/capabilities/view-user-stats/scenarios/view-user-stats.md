---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Stats on a user
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
- text: The Product works out the user's opened, completed and in-progress comics and daily activity
  kind: product
  actor: admin
  entities:
  - entity: reading-progress
    effect: reads
    facts:
    - Last read page
    - Page count
    - Updated
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::user-stats
---

# See a user's reading stats

## Trigger

An admin wants to know what a user has been reading.

## Outcome

The admin sees the user's figures for the last 30 days.

## Edge cases

- The window can be widened up to 365 days.
