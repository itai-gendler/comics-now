---
domain: reading-lists
references:
- kind: code
  role: implementation
  target: server/routes/user/reading-lists.js
- kind: code
  role: implementation
  target: server/services/readingLists.js
---

# Reading List

A person's own named reading order across series and publishers, such as a crossover event. Every person keeps their own lists; a list given to everyone arrives as each person's own copy.

## Information kept

- **Name** — the list's name
- **Description** — what the list is for
- **Comics** — the comics on it, in reading order
- **Position** — where it sits among the person's lists
- **Progress** — how many of its comics the person has read, is reading and has not started
