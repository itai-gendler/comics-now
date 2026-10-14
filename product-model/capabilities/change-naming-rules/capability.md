---
domain: management
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: server/routes/admin/comictagger.js
- kind: code
  role: implementation
  target: server/services/organization.js#formatComicFilename
---

# Change naming rules

An admin arranges the tokens that make a comic's file name, such as series, number and year, with a live preview.
