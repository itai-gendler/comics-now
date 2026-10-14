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
- text: No candidate reaches the review confidence
  kind: condition
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Review confidence
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product records the comic as unmatched
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
    from: Pending
    to: Failed
    facts: []
  contexts:
    web:
      place: web::administration::tag-comics-now
---

# No match is good enough

## Trigger

No candidate reaches the review confidence.

## Outcome

The comic is recorded as unmatched and left untouched.
