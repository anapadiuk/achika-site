# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install        # Install dev dependencies (Tailwind CLI)
npm run dev        # Watch mode: recompiles public/tailwind.css on src/input.css changes
npm run build      # Production build: minified public/tailwind.css
```

No test runner or linter is configured.

## Architecture

Static bilingual marketing site for achika.lt — plain HTML + Tailwind CSS v4. No framework, no bundler, no TypeScript.

- `index.html` — English version (served at `/` or `/en`)
- `lt/index.html` — Lithuanian version (served at `/lt`)
- `src/input.css` — Tailwind entry point (`@import "tailwindcss"`)
- `public/tailwind.css` — **Committed** compiled CSS; no build step required on the host

Both HTML files are self-contained and share no templating system — changes to shared UI (nav, footer, etc.) must be made in both files manually.

`public/tailwind.css` must be rebuilt and committed whenever Tailwind utility classes are added or removed from the HTML files.

## Formatting

Prettier is configured with `printWidth: 120` and `htmlWhitespaceInsensitivity: "css"`. Run `npx prettier --write .` to format.
