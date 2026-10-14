---
domain: tag-comics-now
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/services/tagger.js#clearEnhancedTracking
---

# Clear enhancement history

An admin forgets which comics tagging has already handled, so every comic is considered again and every tag status returns to pending.
