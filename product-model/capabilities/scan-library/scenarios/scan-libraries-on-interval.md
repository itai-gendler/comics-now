---
kind: primary
routes:
  web: Web
steps:
- text: The scan interval has passed
  kind: condition
  unattended: true
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Scan interval
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product adds the comics found since the last scan
  kind: product
  entities:
  - entity: comic
    as: new
    effect: creates
    to: Pending
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Volume
    - Year
    - Creators
    - Summary
    - Cover
    - Page count
    - File name
    - Location
    - Added
  - entity: guided-view
    as: new-view
    effect: creates
    to: Pending
    facts:
    - Panels
    with: new
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product removes the comics whose files are gone
  kind: product
  entities:
  - entity: comic
    as: missing
    effect: removes
    from: Pending
  - entity: guided-view
    as: missing-view
    effect: removes
    from: Pending
    with: missing
  contexts:
    web:
      place: web::administration::general-settings
---

# Scan on the interval

## Trigger

The scan interval has passed since the last scan.

## Outcome

New comics appear and missing ones disappear without anyone asking.

## Edge cases

- A scheduled scan is skipped while tagging is running.
