---
domain: library
relations:
- entity: reading-progress
  verb: has
  cardinality: one-to-many
- entity: guided-view
  verb: has
  cardinality: one-to-one
- entity: pending-match
  verb: awaits
  cardinality: one-to-many
- entity: downloaded-comic
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/services/library-scan.js#scanLibrary
- kind: code
  role: implementation
  target: server/services/library.js#buildLibrary
---

# Comic

One comic archive the Product has found in a library or in the Smart Inbox, with the metadata that places it under a publisher and series. Its state is how far tagging has got: whether it carries the series, publisher, date and issue number a library needs.

## Information kept

- **Title** — the story title, kept empty when it only repeats the series
- **Series** — the series it belongs to
- **Publisher** — the publisher it is filed under
- **Issue number** — its number within the series
- **Volume** — the volume of the series
- **Year** — its publication year, with month and day where known
- **Creators** — writer, pencillers, inkers, colorists, letterers and cover artists
- **Summary** — the synopsis
- **Cover** — the thumbnail made from its first page
- **Page count** — how many pages the archive holds
- **File name** — the archive's name on disk
- **Location** — the library folder or the Smart Inbox it sits in
- **Added** — when the Product first found it

## States

### Pending

Found but not yet confirmed as fully tagged.

### Successful

Carries a series, a publisher, a date and an issue number.

### Failed

Tagging found no acceptable match, a match was skipped, or a save left required tags missing.
