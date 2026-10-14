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
- entity: access-grant
  verb: holds
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/middleware/auth.js#requireAuth
- kind: doc
  role: context
  target: docs/WIKI.md
---

# User

A person who reads the comics their access grants open to them, keeps their own reading lists, progress, devices and reading preferences, and downloads comics to read offline.
