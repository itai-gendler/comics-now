---
kind: alternative
routes:
  mcp: MCP
steps:
- text: The AI Agent triggers detection for a series
  kind: actor
  actor: ai-agent
  entities: []
  contexts:
    mcp:
      place: mcp
- text: The Product queues the series' comics that have no Guided View
  kind: product
  actor: ai-agent
  entities:
  - entity: guided-detection-run
    effect: creates
    to: Running
    facts:
    - Scope
    - Re-run completed
    - Queue
  - entity: guided-view
    effect: reads
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
---

# An AI agent triggers detection

## Trigger

An admin asks their AI agent to prepare a series for Guided View.

## Outcome

The series' comics without a Guided View get one.
