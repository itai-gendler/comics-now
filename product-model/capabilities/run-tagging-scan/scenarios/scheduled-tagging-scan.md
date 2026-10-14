---
kind: primary
routes:
  web: Web
steps:
- text: The tagging schedule has elapsed
  kind: condition
  unattended: true
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Tagging schedule
    - Re-scan tagged comics
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product starts a tagging scan of the Smart Inbox
  kind: product
  entities:
  - entity: tagging-scan
    effect: creates
    to: Running
    facts:
    - Mode
    - Output
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product writes the tags of confident matches
  kind: product
  entities:
  - entity: comic
    effect: changes
    from: Pending
    to: Successful
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Year
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product finishes the scan
  kind: product
  entities:
  - entity: tagging-scan
    effect: changes
    from: Running
    to: Finished
    facts:
    - Results
  contexts:
    web:
      place: web::administration::tag-comics-now
---

# Tag on the schedule

## Trigger

The tagging schedule has elapsed.

## Outcome

New comics in the Smart Inbox are tagged without anyone asking.

## Edge cases

- A schedule of 0 minutes runs no scheduled scans.
