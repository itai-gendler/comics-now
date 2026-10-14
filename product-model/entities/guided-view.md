---
domain: guided-reader
references:
- kind: code
  role: implementation
  target: server/services/guided-reader.js
- kind: code
  role: implementation
  target: server/routes/user/pages.js
---

# Guided View

The panel and speech-bubble map of one comic that lets anyone with access read it panel by panel. It is generated once by the panel detector (or written by an AI agent) and shared by every reader of that comic.

## Information kept

- **Panels** — the panel and speech-bubble regions of each page, in reading order
- **Source** — whether the panel detector made it or an AI agent wrote it
- **Error** — why detection last failed

## States

### Pending

No panel map yet.

### Processing

The panel detector is working on the comic now.

### Completed

The panel map is ready to read.

### Failed

Detection did not produce a panel map.
