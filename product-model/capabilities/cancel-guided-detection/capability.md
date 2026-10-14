---
domain: guided-reader
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/services/guided-reader.js#cancelAll
- kind: code
  role: implementation
  target: server/services/guided-reader.js#cancelCurrent
---

# Cancel Guided Detection

An admin cancels the whole detection run, or only the comic being processed so the rest of the queue continues.
