---
references:
- kind: code
  role: implementation
  target: server/db.js#resolveReadingModes
- kind: code
  role: implementation
  target: server/routes/user/reading.js
---

# Reading Preference

A person's choice of reading direction and scroll mode for one comic, series, publisher or library. The most specific choice wins: a comic's own choice over its series, its series over its publisher, its publisher over its library.

## Information kept

- **Level** — Comic, Series, Publisher or Library
- **Target** — the comic, series, publisher or library it applies to
- **Manga mode** — right-to-left reading on, off, or left to the level above
- **Continuous mode** — one long vertical scroll on, off, or left to the level above
