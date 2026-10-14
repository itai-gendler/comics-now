---
type: agent
actors:
- ai-agent
references:
- kind: code
  role: implementation
  target: mcp/comics_mcp/server.py
- kind: doc
  role: intent
  target: mcp/README.md
---

# Comics Now! MCP server

The Model Context Protocol server bundled with Comics Now!: tools an AI agent calls to search the library, build reading lists, read covers, write ComicInfo tags, trigger Guided View detection and write Guided Views.
