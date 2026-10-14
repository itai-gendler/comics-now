---
kind: primary
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
- text: The Product starts a tagging scan of the Smart Inbox
  kind: product
  actor: admin
  entities:
  - entity: tagging-scan
    effect: creates
    to: Running
    facts:
    - Mode
    - Output
  - entity: server-settings
    effect: reads
    facts:
    - Smart Inbox folder
    - Enabled sources
  contexts:
    web:
      place: web::administration::tag-comics-now
- text: The Product finds a match at or above the auto-accept confidence and writes its tags
  kind: product
  actor: admin
  entities:
  - entity: server-settings
    effect: reads
    facts:
    - Auto-accept confidence
    - Metadata storage
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
      place: web::administration::tag-comics-now
- text: The Product finishes the scan and reports the results
  kind: product
  actor: admin
  entities:
  - entity: tagging-scan
    effect: changes
    from: Running
    to: Finished
    facts:
    - Results
    - Output
  contexts:
    web:
      place: web::administration::tag-comics-now
---

# Tag the Smart Inbox

## Trigger

An admin has dropped new comics into the Smart Inbox.

## Outcome

Comics matched confidently carry their tags and are Successful.

## Decision points

### Is Gemini comparing the covers?

Is Gemini cover matching on, with a key, the agreement accepted and requests left today?

- Yes → Gemini compares the comic's cover with each candidate's and its verdict sets the confidence
- No → covers are compared by their image fingerprints

## Edge cases

- Comics that already carry complete ComicInfo, or that tagging has already enhanced, are skipped.
- Comics in sub-folders of the Smart Inbox are not tagged.
- When anything was tagged the libraries are scanned again.
