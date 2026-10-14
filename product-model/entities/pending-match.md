---
domain: tag-comics-now
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#runComicTagger
- kind: code
  role: implementation
  target: server/routes/admin/comictagger.js
---

# Pending Match

A comic from the Smart Inbox that tagging matched only with middling confidence, waiting for an admin to apply one of its candidate matches or skip it. Tagging waits on it before going on.

## Information kept

- **File** — the comic file being matched
- **Candidates** — each candidate's title, issue, year, publisher, cover, confidence and source
- **Cover preview** — the comic's own first page, to compare against

## States

### Awaiting review

Tagging is waiting for the admin's choice.

### Applied

The admin applied a candidate.

### Skipped

The admin skipped it and the comic was recorded as unmatched.
