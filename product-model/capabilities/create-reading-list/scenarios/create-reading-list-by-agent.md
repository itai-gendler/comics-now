---
kind: alternative
routes:
  mcp: MCP
steps:
- text: The AI Agent searches the library for the event's issues
  kind: actor
  actor: ai-agent
  entities:
  - entity: comic
    effect: reads
    facts:
    - Title
    - Series
    - Issue number
    - Year
  - entity: library
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
- text: The AI Agent creates a reading list with those comics in reading order
  kind: actor
  actor: ai-agent
  entities:
  - entity: reading-list
    effect: reads
    facts: []
  - entity: comic
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
- text: The Product creates the reading list for the admin
  kind: product
  actor: ai-agent
  entities:
  - entity: reading-list
    effect: creates
    facts:
    - Name
    - Description
    - Comics
    - Position
  - entity: admin
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
---

# An AI agent builds a reading list

## Trigger

An admin asks their AI agent for a reading order of a crossover event.

## Outcome

The admin has a new reading list with the comics in the agent's order.

## Edge cases

- An agent can create many lists in one request; each list without a name is reported and the others are created.
