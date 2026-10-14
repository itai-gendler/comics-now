---
entities:
- entity: server-settings
  shows:
  - Gemini model
  - Gemini cover matching
  - Gemini daily cap
  - Gemini requests today
  - Gemini agreement
  collects:
  - Gemini API key
  - Gemini model
  - Gemini cover matching
  - Gemini daily cap
  - Gemini agreement
references:
- kind: code
  role: implementation
  target: public/js/comictagger.js
- kind: code
  role: implementation
  target: server/routes/admin/gemini.js
---

# Gemini

Gemini cover matching: key, model, on or off, daily cap and today's usage, behind the compliance agreement.
