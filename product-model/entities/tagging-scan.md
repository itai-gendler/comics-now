---
domain: tag-comics-now
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#runComicTagger
---

# Tagging Scan

One pass of Tag Comics Now! over the comics in the Smart Inbox, looking each up in the enabled metadata sources and writing tags.

## Information kept

- **Mode** — Default, Rescan Unmatched, or Force Re-scan of comics that already carry ComicInfo
- **Results** — how many comics were tagged, sent to review, skipped and failed
- **Output** — the live log of what it did to each comic

## States

### Running

Working through the Smart Inbox.

### Finished

Every comic was processed.

### Cancelled

An admin stopped it.
