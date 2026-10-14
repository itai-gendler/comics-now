---
singleton: true
references:
- kind: code
  role: implementation
  target: server/config.js
- kind: code
  role: implementation
  target: server/settings.js
---

# Server Settings

The server's one set of settings: how it scans, stores metadata, tags, matches covers with Gemini, runs Guided View detection and names and files comics, plus who the admin is.

## Information kept

- **Admin email** — the email of the person who holds the Admin role, set in the server configuration
- **Sign-in** — whether Cloudflare Access sign-in is on
- **Trusted networks** — network addresses whose direct connections act as the built-in admin account
- **Scan interval** — minutes between automatic library scans, from 1 to 1440
- **Allowed formats** — CBZ only, CBR only, or both
- **Metadata storage** — where saved metadata goes: inside the CBZ archive, a ComicInfo sidecar file, or the database only
- **ComicVine API key** — the key used for ComicVine lookups
- **Smart Inbox folder** — the folder new comics arrive in for tagging and filing
- **Tagging schedule** — minutes between scheduled tagging scans, 0 for none
- **Auto-accept confidence** — the match confidence at or above which tags are applied without review
- **Review confidence** — the match confidence below which a comic is recorded as unmatched
- **Enabled sources** — which metadata sources tagging searches: ComicVine, Metron, GCD, League of Comic Geeks, Goodreads, Blackwell's, Waterstones, Google Books, Amazon, Forbidden Planet
- **Re-scan tagged comics** — whether scheduled tagging scans also re-scan comics that already carry ComicInfo
- **Source credentials** — the Metron sign-in and Google Books key
- **Tagger service port** — the port of the tagging service the server runs
- **Gemini API key** — the key for Gemini cover matching
- **Gemini model** — the Gemini Flash-Lite model used
- **Gemini cover matching** — whether tagging compares covers with Gemini
- **Gemini daily cap** — the most Gemini requests per day, counted from midnight Pacific time
- **Gemini agreement** — whether the admin has accepted the Gemini compliance agreement
- **Gemini requests today** — how many Gemini requests have been made since midnight Pacific time
- **Guided auto-run** — whether detection runs on comics a library scan has just added
- **Guided schedule** — whether detection runs on a schedule, and every how many hours or days
- **Naming rules** — the ordered tokens that make a comic's file name
- **Folder rules** — the folder levels a comic is filed under in a library
