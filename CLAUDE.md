# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Expected behavior

Challenge the developer's way of thinking, don't validate it. When a plan or technical decision is proposed:

- Point out flaws, edge cases and blind spots
- Disagree when the logic is weak or there are unsupported assumptions
- Say directly when something is a bad idea, instead of making it work anyway

No encouragement or positivity needed. Critical thinking and direct corrections are needed.

## Project structure

- Static HTML project — single `index.html` at root, no framework, no build step
- Images: `public/images/1.jpeg`, `2.jpeg`, `3.jpeg` (relative to root)
- Email delivery: EmailJS CDN; credentials (`EJS_PUB`, `EJS_SVC`, `EJS_TPL`) at top of inline `<script>` in `index.html`
- Recipient email: `julianamarilest809@gmail.com` — set inside the EmailJS template, not in code

## Design system

- Palette: `#000` / `#fff` / grays only — no color
- Fonts: Bebas Neue (display), Cormorant Garamond italic (body/questions), Space Mono (UI) — never Inter/Arial/Roboto
- Mobile-first; desktop breakpoint at 768px (layout) and 1100px (two-column grid)

## Quick start

```bash
# Preview in browser (no build step needed)
open index.html              # macOS
xdg-open index.html         # Linux
python3 -m http.server 8080  # o servir localmente para paths de imágenes correctos
```

## Code organization

All CSS and JS live inline inside `index.html` — there are no external `.css` or `.js` files.
Steps are identified as `#s0` (hero) through `#s10` (success). Navigation via `go(n)`.
Form answers accumulate in the `fd` object at the top of the `<script>` block.

## Before editing

- Replace the 3 `TODO` constants (`EJS_PUB`, `EJS_SVC`, `EJS_TPL`) in `index.html` or email sending will silently fail
- `public/` contains only the 3 images — nothing else should go there