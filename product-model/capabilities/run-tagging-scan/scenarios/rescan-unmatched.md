---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Rescan Unmatched
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product starts a tagging scan of only the comics recorded as unmatched
  kind: product
  actor: admin
  entities:
  - entity: tagging-scan
    effect: creates
    to: Running
    facts:
    - Mode
    - Output
  - entity: comic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product tags the comics that now match confidently
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
    from: Failed
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
---

# Rescan unmatched comics

## Trigger

An admin has enabled more sources and wants another try at comics recorded as unmatched.

## Outcome

Comics that now match are tagged; the rest stay unmatched.
