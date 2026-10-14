---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Force Re-scan
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product starts a tagging scan that includes comics already carrying ComicInfo
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
- text: The Product re-tags the comics with a confident match
  kind: product
  actor: admin
  entities:
  - entity: comic
    effect: changes
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

# Force a re-scan of tagged comics

## Trigger

An admin wants comics that already carry ComicInfo looked up again.

## Outcome

Those comics are searched again and re-tagged where a better match is found.
