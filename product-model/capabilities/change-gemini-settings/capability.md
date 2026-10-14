---
domain: tag-comics-now
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/gemini.js
- kind: code
  role: implementation
  target: server/services/gemini-quota.js#incrementDailyUsage
---

# Change Gemini settings

An admin connects Gemini cover matching: accepting the compliance agreement, entering the API key, choosing a Flash-Lite model, turning matching on and setting a daily cap.
