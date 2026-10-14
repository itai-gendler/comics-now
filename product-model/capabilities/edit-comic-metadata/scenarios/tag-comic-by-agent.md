---
kind: alternative
routes:
  mcp: MCP
steps:
- text: The AI Agent reads the comic's cover at full resolution
  kind: actor
  actor: ai-agent
  entities:
  - entity: comic
    effect: reads
    facts:
    - Cover
  contexts:
    mcp:
      place: mcp
- text: The AI Agent writes the series, publisher, year and issue number it identified
  kind: actor
  actor: ai-agent
  entities: []
  contexts:
    mcp:
      place: mcp
- text: The Product saves the tags to the comic and writes its ComicInfo
  kind: product
  actor: ai-agent
  entities:
  - entity: comic
    effect: changes
    from: Pending
    to: Successful
    facts:
    - Series
    - Publisher
    - Year
    - Issue number
  contexts:
    mcp:
      place: mcp
---

# An AI agent tags a comic from its cover

## Trigger

An admin asks their AI agent to identify an untagged comic.

## Outcome

The comic carries the tags the agent wrote.
