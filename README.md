# achika-site — Marketing site

Static marketing site for [achika.lt](https://achika.lt). Two languages: English (root) and Lithuanian (`/lt`).

## Stack

- Plain HTML + [Tailwind CSS v4](https://tailwindcss.com)
- No frameworks, no bundler
- Tailwind built via `@tailwindcss/cli`

## Structure

```
index.html          # English (routes: / and /en)
lt/index.html       # Lithuanian (/lt)
public/
  tailwind.css      # Built CSS — commit this
  logo.svg          # Horizontal logo (icon + text)
  favicon.svg       # Icon only
src/
  input.css         # Tailwind entry point (@import "tailwindcss")
```

## Development

Install dependencies (first time only):

```bash
npm install
```

Watch mode — rebuilds CSS on every file change:

```bash
npm run dev
```

Preview locally with [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) (VS Code) or any static file server.

## Build

Minified CSS for production:

```bash
npm run build
```

Always run before committing if you changed any Tailwind classes in HTML.

## Languages

| Route | File | Language |
|-------|------|----------|
| `/` or `/en` | `index.html` | English |
| `/lt` | `lt/index.html` | Lithuanian |

Language switcher is in the header on both pages.

## Deployment

Static files only — deploy `index.html`, `lt/`, and `public/` to any static host (Netlify, Vercel, GitHub Pages, etc.).

No build step required on the host — `public/tailwind.css` is committed.
