---
scope: The Comics Now! server, its web app and PWA client, the bundled tagging service and the MCP server.
method: Static inspection of source, configuration and documentation at the pinned commit; nothing was run.
covered:
- description: Express server entry, configuration, settings and database schema
  paths:
  - server.js
  - server/config.js
  - server/settings.js
  - server/db.js
  - server/constants.js
  - server/validation.js
  - server/utils.js
- description: Sign-in, roles, access resolution and impersonation
  paths:
  - server/middleware/
  - server/access-control.js
- description: API routes for users and admins
  paths:
  - server/routes/
- description: Library scanning, conversion, metadata, tagging, Gemini, organization, guided detection and reading-list services
  paths:
  - server/services/
  - server/utils/
- description: 'Web app and PWA client: library, reader, reading lists, downloads, devices, settings and Tag Comics Now! panel'
  paths:
  - public/
- description: Tagging service that searches metadata sources and writes ComicInfo
  paths:
  - tagger/app.py
  - tagger/tagger_app/
- description: MCP server tools for AI agents
  paths:
  - mcp/comics_mcp/
exclusions:
- description: Automated tests
  paths:
  - tests/
  - tagger/tests/
  - mcp/tests/
- description: Bundled publisher logos, icons, styles and ONNX model weights
  paths:
  - logos/
  - icons/
  - styles/
  - models/
- description: Packaging, container, CI and startup dependency checks
  paths:
  - bin/
  - Dockerfile
  - docker-compose.yml
  - docker-entrypoint.sh
  - .github/
  - scripts/
  - server/startup/
  - vite.config.js
  - jest.config.js
  - playwright.config.js
  - package.json
  - package-lock.json
- description: Documentation and screenshots
  paths:
  - docs/
unmapped:
- description: Server logger and the log viewers and streams built on it
  paths:
  - server/logger.js
- description: Reader display-control modules (preview grid, fit, orientation, e-ink, cinema pan, hot zoom, page jump)
  paths:
  - public/js/viewer/
- description: Download queue history, pause and retry modules and the service worker
  paths:
  - public/js/offline/download-history.js
  - public/service-worker.js
- description: Reading-list bulk, sync-to-all and delete-everywhere handlers
  paths:
  - server/services/readingLists.js
- description: Tagging service web page and scan-log persistence
  paths:
  - tagger/templates/
  - tagger/tagger_app/persistence/
- description: MCP launcher and configuration
  paths:
  - mcp/run.sh
  - mcp/requirements.txt
- description: Publisher logo lookup and page image cache services
  paths:
  - server/services/library-logos.js
  - server/services/page-cache.js
limitations:
- description: Metadata-source scrapers and cover hashing, whose matching quality depends on third-party sites
  paths:
  - tagger/tagger_app/sources/
  - tagger/tagger_app/core/covers.py
- description: Gemini prompts and cover verdicts, whose outcome depends on the model
  paths:
  - server/services/gemini-cover.js
  - server/services/gemini-metadata.js
---

# Coverage
