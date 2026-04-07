---
title: Design System
tags: [project, design]
status: active
---

# Design System

Noctodeus uses a minimal dark aesthetic with intentional blur.

## Color Palette

| Token | Hex | Usage |
| --- | --- | --- |
| background | #09090b | App base |
| card | #0f0f12 | Sidebar, panels |
| popover | #18181b | Dropdowns, modals |
| border | #27272a | All borders |
| foreground | #fafafa | Primary text |
| muted-foreground | #a1a1aa | Secondary text |
| accent | #6366f1 | Brand indigo |

## Typography

Three-tier font strategy:

1. **Mono** — Berkeley Mono, JetBrains Mono (UI chrome, code)
2. **Sans** — Inter (labels, buttons)
3. **Content** — Source Serif 4 (reading, editor body)

## Blur Rules

- **Backdrops** (modals, quick open): 8px blur
- **Floating menus** (context menu, dropdowns): 12px blur
- **Minimap**: 16px blur
- **Everything else**: solid backgrounds, no blur

## Motion

Single timing: **150ms** for menus, **250ms** for panels, **450ms** for modals.
Single easing: `cubic-bezier(0.16, 1, 0.3, 1)` (expo-out).

See [[reference/keyboard-shortcuts]] for interaction patterns.
