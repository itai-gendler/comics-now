---
entities:
- entity: library
  shows:
  - Folder
  - Organization
  collects:
  - Folder
  - Organization
- entity: server-settings
  shows:
  - Scan interval
  - Allowed formats
  - Metadata storage
  - ComicVine API key
  collects:
  - Scan interval
  - Allowed formats
  - Metadata storage
  - ComicVine API key
references:
- kind: code
  role: implementation
  target: public/js/settings.js
---

# General settings

The server's libraries, scan interval, ComicVine key, allowed formats and metadata storage, with Scan Now and Full Scan.
