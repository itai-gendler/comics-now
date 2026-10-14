---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Run on the tagging console
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product finds candidates between the review and auto-accept confidence
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Review confidence
    - Auto-accept confidence
  - entity: comic
    effect: reads
    facts:
    - File name
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product holds the comic for review with its candidates and pauses the scan
  kind: product
  actor: admin
  entities:
  - entity: pending-match
    effect: creates
    to: Awaiting review
    facts:
    - File
    - Candidates
    - Cover preview
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::tag-comics-now
---

# A match needs review

## Trigger

The best match is above the review confidence but below the auto-accept confidence.

## Outcome

The comic waits on the Matches tab and tagging waits for the admin's choice.
