---
kind: edge
routes:
  web: Web
steps:
- text: The Admin chooses Apply on a candidate
  kind: actor
  actor: admin
  entities:
  - entity: pending-match
    effect: reads
    facts:
    - Candidates
  contexts:
    web:
      place: web::administration::matches
- text: The Product writes the tags and finds a required tag missing
  kind: product
  actor: admin
  entities:
  - entity: pending-match
    effect: changes
    from: Awaiting review
    to: Applied
    facts: []
  - entity: comic
    effect: changes
    from: Pending
    to: Failed
    facts:
    - Title
    - Series
  contexts:
    web:
      place: web::administration::matches
---

# The applied match lacks required tags

## Trigger

The chosen candidate has no date or no issue number.

## Outcome

The tags are written but the comic is Failed.
