---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Scan Now
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
- text: A PDF or CBR file sits in the Smart Inbox
  kind: condition
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Smart Inbox folder
    - Allowed formats
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product converts it to CBZ and adds the comic
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: creates
    to: Pending
    facts:
    - Title
    - Series
    - Publisher
    - Cover
    - Page count
    - File name
    - Location
    - Added
  contexts:
    web:
      place: web::administration::general-settings
---

# Convert PDF and CBR files in the Smart Inbox

## Trigger

A scan finds PDF or CBR files in the Smart Inbox while only CBZ is allowed.

## Outcome

The files are CBZ comics in the Smart Inbox, ready for tagging.

## Edge cases

- Outside the Smart Inbox PDF files are skipped and CBR files are included only when CBR is allowed.
