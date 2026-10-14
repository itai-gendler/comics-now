---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Download for Offline on a comic
  kind: actor
  actor: user
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::library::series
- text: The Product queues the comic
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: creates
    to: Queued
    facts:
    - Progress
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::library::downloads
- text: The Product downloads its pages in the background
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: changes
    from: Queued
    to: Downloading
    facts:
    - Progress
  contexts:
    web:
      place: web::library::downloads
- text: The Product keeps the pages in this browser
  kind: product
  actor: user
  entities:
  - entity: downloaded-comic
    effect: changes
    from: Downloading
    to: Downloaded
    facts:
    - Pages
    - Progress
    - Size
  contexts:
    web:
      place: web::library::downloads
---

# Download a comic

## Trigger

A person on a phone wants a comic for a flight.

## Outcome

The comic is downloaded and readable offline.

## Edge cases

- A comic already downloaded is not queued again.
- An interrupted download resumes from where it stopped.
- On Android the download carries on with the browser closed.
