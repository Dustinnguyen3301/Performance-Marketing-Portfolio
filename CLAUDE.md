# CLAUDE.md — Performance Marketing Portfolio

Personal portfolio of Dustin Nguyen (Performance Marketing Specialist, Vietnam).
Live: https://dustinngmarketing.com/

## Stack
- Plain static HTML + one shared `style.css`. No framework, no build step, no JS bundler.
- Fonts: Manrope (text) + DM Mono (labels), loaded from Google Fonts.
- Images: `.webp` for case-study visuals, kept in the repo root next to the HTML.

## Pages
- `index.html` — landing page (Home, Expertise, Experience, Key projects, About, Education, Certifications, Contact)
- Case studies: `avene.html`, `logitech.html`, `homecredit-brand-awareness.html`,
  `homecredit-customer-acquisition.html`, `homecredit-app-retention.html`

## Deploy
- GitHub Pages, served from the `main` branch (repo root). Pushing to `main` = live in ~1–2 minutes.
- Work branches (`claude/...`) are NOT live until merged into `main`.

## Workflow with the Claude app (briefs)
- Content, copy and mockups are prepared in the Claude app and saved to `_brief/`:
  - `_brief/brief.md` — the current change request. Read this first.
  - `_brief/content/` — finished copy (markdown) to put into the HTML.
  - `_brief/mockups/` — approved mockups (HTML/images) to match visually.
  - `_brief/done/` — old briefs, archived after they are shipped.
- `_brief/` is internal: never link to it from the site. (Folders starting with `_`
  are not published by GitHub Pages' Jekyll build.)
- When a brief is shipped: move `brief.md` to `_brief/done/YYYY-MM-DD-<topic>.md`
  and reset `brief.md` from the template at the bottom of `_brief/README.md`.

## Conventions
- Site copy is in English. Keep the tone concise, data-led, first person.
- Numbers: use “VND 5B”, “20+ brands” style; keep figures consistent across pages
  (meta description, og tags and body text).
- After changing `style.css`, bump the cache-buster in every page (`style.css?v=N`).
- When editing `index.html` meta/OG text, keep `description`, `og:description`
  and visible hero copy in sync.
- New images: `.webp`, lowercase-hyphen names, `<brand>-<platform>-<lang>.webp`.
- Preview locally: `python3 -m http.server 8000` → http://localhost:8000

## Before pushing
1. Show the diff to the user.
2. Check every page still links correctly and nothing in `_brief/` is linked.
3. Merge into `main` and push only after the user confirms.
