---
kind: alternative
routes:
  mcp: MCP
steps:
- text: The AI Agent adds comics to a reading list of the admin
  kind: actor
  actor: ai-agent
  entities:
  - entity: reading-list
    effect: reads
    facts:
    - Name
  - entity: admin
    effect: reads
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
- text: The Product appends them to the reading list
  kind: product
  actor: ai-agent
  entities:
  - entity: reading-list
    effect: changes
    facts:
    - Comics
  contexts:
    mcp:
      place: mcp
---

# An AI agent adds comics to a list

## Trigger

An admin's AI agent extends one of the admin's lists.

## Outcome

The comics follow the list's existing comics.
