---
kind: person
acts: external
relations:
- entity: account
  verb: signs in as
  cardinality: one-to-one
- entity: reading-list
  verb: owns
  cardinality: one-to-many
- entity: device
  verb: owns
  cardinality: one-to-many
- entity: reading-progress
  verb: keeps
  cardinality: one-to-many
- entity: reading-preference
  verb: sets
  cardinality: one-to-many
- entity: library
  verb: manages
  cardinality: many-to-many
- entity: ai-agent
  verb: connects
  cardinality: one-to-many
- entity: impersonation
  verb: starts
  cardinality: one-to-many
- entity: guided-detection-run
  verb: starts
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/middleware/auth.js#requireAdmin
- kind: doc
  role: context
  target: docs/WIKI.md
---

# Admin

The person who runs the server: they read everything, manage libraries and users, tag and organize comics and generate Guided Views, as well as reading like any user.
