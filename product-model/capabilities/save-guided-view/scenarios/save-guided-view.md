---
kind: primary
routes:
  mcp: MCP
steps:
- text: The AI Agent lists the comic's pages and reads each page image
  kind: actor
  actor: ai-agent
  entities:
  - entity: comic
    effect: reads
    facts:
    - Page count
  - entity: guided-view
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
- text: The AI Agent sends the panel regions of each page in reading order
  kind: actor
  actor: ai-agent
  entities: []
  contexts:
    mcp:
      place: mcp
- text: The Product keeps the map as the comic's Guided View
  kind: product
  actor: ai-agent
  entities:
  - entity: guided-view
    effect: changes
    from: Pending
    to: Completed
    facts:
    - Panels
    - Source
  - entity: comic
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
---

# An AI agent writes a Guided View

## Trigger

An admin asks their AI agent to author the panels of a comic the detector handles badly.

## Outcome

The comic's Guided View is the agent's map and is ready to read.

## Edge cases

- Regions may be sent as fractions of the page or in pixels.
