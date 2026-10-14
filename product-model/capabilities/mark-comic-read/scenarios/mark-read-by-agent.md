---
kind: alternative
routes:
  mcp: MCP
steps:
- text: The AI Agent asks to mark a series read
  kind: actor
  actor: ai-agent
  entities: []
  contexts:
    mcp:
      place: mcp
- text: The Product sets the admin's progress on every issue of the series to its last page
  kind: product
  actor: ai-agent
  entities:
  - entity: reading-progress
    effect: changes
    facts:
    - Last read page
    - Page count
    - Updated
  - entity: admin
    effect: reads
    facts: []
  contexts:
    mcp:
      place: mcp
---

# An AI agent marks comics read

## Trigger

An admin asks their AI agent to record comics they have read.

## Outcome

The comics show as read for that admin.
