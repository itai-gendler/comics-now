---
domain: tag-comics-now
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#runComicTagger
- kind: code
  role: implementation
  target: tagger/app.py
- kind: code
  role: implementation
  target: server/services/gemini-tagger.js#installTaggerHook
- kind: code
  role: implementation
  target: server/routes/admin/comictagger.js
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Run a tagging scan

Tag Comics Now! goes through the comics in the Smart Inbox, searches the enabled metadata sources, compares covers, and by match confidence applies tags, holds the comic for an admin's review, or records it as unmatched. An admin starts it in one of three modes, or it runs on its schedule.
