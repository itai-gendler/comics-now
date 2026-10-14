---
kind: primary
routes:
  web: Web
steps:
- text: The Admin compares the candidates with the first page shown and chooses Apply on one
  kind: actor
  actor: admin
  entities:
  - entity: pending-match
    effect: reads
    facts:
    - File
    - Candidates
    - Cover preview
  contexts:
    web:
      place: web::administration::matches
- text: The Product writes the candidate's tags into the comic
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
    to: Successful
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
    - Volume
    - Year
    - Creators
    - Summary
  contexts:
    web:
      place: web::administration::matches
- text: The Product resumes the tagging scan
  kind: product
  actor: admin
  entities:
  - entity: tagging-scan
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::matches
---

# Apply a candidate

## Trigger

A comic is waiting for review.

## Outcome

The comic carries the chosen candidate's tags and is Successful.
