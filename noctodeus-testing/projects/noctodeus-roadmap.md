---
title: Noctodeus Roadmap
tags: [planning, Planning]
status: active
priority: high
---
# Noctodeus Roadmap

Tracking what's built and what's next. See [[feature-showcase]] for demos.

## Completed

- [x] TipTap rich text editor with markdown serialization
- [x] Wiki links with `[[backlinks]]` and graph view
- [x] Full-text search across all notes (FTS5)
- [x] Slash command menu with block types
- [x] Tables, math, highlight, subscript, superscript
- [x] File tree with pin/unpin stars
- [x] Export to Markdown, HTML, CSV
- [x] Settings with auto-save, font size, character count
- [x] Find & replace in editor (Cmd+F)
- [x] Inline title editing
- [x] Core switcher (multiple vaults)
- [x] Cross-platform shortcuts (Cmd/Ctrl)
- [x] anime.js entry animations

## In Progress

- [ ] Light theme support
- [ ] Note details panel (word count, TOC)
- [ ] Edit/view mode toggle

## Planned

- [ ] Daily notes with calendar
- [ ] Properties panel for YAML frontmatter
- [ ] Queryable database views
- [ ] Task extraction across vault
- [ ] Canvas / infinite whiteboard
- [ ] Plugin API

## Architecture

| Layer | Technology |
| --- | --- |
| Desktop | Tauri 2 (Rust) |
| Frontend | SvelteKit + Svelte 5 |
| Editor | TipTap 3 + ProseMirror |
| Database | SQLite with FTS5 |
| Styling | Tailwind v4 + shadcn-svelte |
| Animation | anime.js v4 |
