---
appliesTo:
- type: capability
  id: run-tagging-scan
- type: entity
  id: server-settings
  facts:
  - Gemini daily cap
  - Gemini requests today
references:
- kind: code
  role: implementation
  target: server/services/gemini-quota.js#incrementDailyUsage
- kind: code
  role: implementation
  target: server/services/gemini-tagger.js#installTaggerHook
---

# Gemini is used at most the daily cap times a day

Each day, counted from midnight Pacific time, tagging uses Gemini until the daily cap (450 by default) is reached and then compares covers by their image fingerprints instead.
