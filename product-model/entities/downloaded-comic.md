---
domain: downloads
references:
- kind: code
  role: implementation
  target: public/js/offline/downloads.js
- kind: code
  role: implementation
  target: public/js/offline/download-actions.js#downloadComic
---

# Downloaded Comic

A comic saved in this browser for offline reading, with its pages and progress. It belongs to the browser it was downloaded in.

## Information kept

- **Pages** — the comic's pages stored in the browser
- **Progress** — how much of it has downloaded
- **Size** — the space it takes on the device

## States

### Queued

Waiting in the download queue.

### Downloading

Pages are arriving.

### Downloaded

Readable offline.

### Failed

The download stopped with an error.
