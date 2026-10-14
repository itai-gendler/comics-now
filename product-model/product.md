---
id: comics-now
summary: 'A self-hosted comic library server and reader: a publisher, series and issue catalogue, per-user access, reading lists, cross-device progress, guided panel reading and multi-source metadata tagging.'
category: media-library
tags:
- comics
- self-hosted
- reader
- pwa
- metadata
authors:
- name: ComicsNow
  url: https://github.com/ComicsNow
license: AGPL-3.0
languages:
- en
limitations:
- People sign in through Cloudflare Access; the Product has no sign-in page or passwords of its own.
- There are two fixed roles, Admin and User, and the admin is the person whose email matches the admin email the server is configured with.
- Comics are read from CBZ and CBR files in folders on the server; PDF and CBR files are converted to CBZ only inside the Smart Inbox.
- Comics are downloaded for offline reading only on phones and tablets, and downloads live in that browser alone.
- Without sign-in configured, everyone who reaches the server uses the built-in admin account.
---

# Comics Now!

Comics Now! turns folders of comic archives on a server into a library that
signed-in people browse by publisher, series and issue (or by folder), read in
the browser or as an installed app, and pick up on any device where they left
off. Admins decide which libraries, publishers, series or folders each user may
read, tag comics with metadata from online sources (with optional Gemini cover
matching), file them into libraries by naming and folder rules, and generate
Guided View panel maps that everyone can then read panel by panel. Reading lists
gather issues across series into one reading order. An AI assistant can work on
the library through the bundled MCP server.

## Intent

"The modern, self-hosted comic book library server, smart reader, and
AI-augmented cataloging platform." It re-imagines a comic library "as a modern,
intelligent web application designed for desktops, tablets, and phones", built
"from the ground up for comics" for collectors and "shared family/community
servers", where an admin can "share specific sections of your collection with
family or friends without exposing your entire library".
