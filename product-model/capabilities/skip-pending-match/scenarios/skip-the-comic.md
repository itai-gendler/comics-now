---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Skip
  kind: actor
  actor: admin
  entities:
  - entity: pending-match
    effect: reads
    facts:
    - File
    - Candidates
  contexts:
    web:
      place: web::administration::matches
- text: The Product records the comic as unmatched and resumes the scan
  kind: product
  actor: admin
  entities:
  - entity: pending-match
    effect: changes
    from: Awaiting review
    to: Skipped
    facts: []
  - entity: comic
    effect: changes
    from: Pending
    to: Failed
    facts: []
  contexts:
    web:
      place: web::administration::matches
---

# Skip the comic

## Trigger

None of the candidates is the comic.

## Outcome

The comic is recorded as unmatched and left untouched.
