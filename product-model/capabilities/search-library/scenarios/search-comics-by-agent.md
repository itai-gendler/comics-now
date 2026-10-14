---
kind: alternative
routes:
  mcp: MCP
steps:
- text: The AI Agent searches for a title
  kind: actor
  actor: ai-agent
  entities: []
  contexts:
    mcp:
      place: mcp
- text: The Product returns the matching comics
  kind: product
  actor: ai-agent
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
    - Publisher
    - Issue number
  contexts:
    mcp:
      place: mcp
---

# An AI agent searches the library

## Trigger

An AI agent looks for comics to work on.

## Outcome

The agent has the matching comics with their ids and metadata.
