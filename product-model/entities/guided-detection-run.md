---
domain: guided-reader
references:
- kind: code
  role: implementation
  target: server/services/guided-reader.js#runWorker
---

# Guided Detection Run

One run of the panel detector over a queue of comics, in library, publisher, series and issue order.

## Information kept

- **Scope** — every library, or one library, publisher, series or comic
- **Re-run completed** — whether comics that already have a Guided View are detected again
- **Current comic** — the comic being processed now
- **Queue** — the comics still waiting

## States

### Running

Working through its queue.

### Finished

The queue is empty.

### Cancelled

An admin cancelled the whole run.
