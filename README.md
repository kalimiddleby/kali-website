# Kali Middleby — personal research website (Quarto scaffold)

This is a working Quarto website project: About, Research, Grants, Publications, Media, and Updates pages, styled to be plain and uncluttered. Everything is placeholder content marked with HTML comments (`<!-- ... -->`) telling you what to replace.

## Getting it live (free, via GitHub Pages)

1. **Create a GitHub repository.** Go to github.com → New repository → name it something like `kali-website` (or `<yourusername>.github.io` if you want it at the root of your GitHub Pages domain instead of a subpath) → keep it public → don't initialize with a README (you already have one).

2. **Push this project to it.** From inside this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial site scaffold"
   git branch -M main
   git remote add origin https://github.com/<yourusername>/kali-website.git
   git push -u origin main
   ```

3. **Turn on GitHub Pages, sourced from the `gh-pages` branch.** In your repo on GitHub: Settings → Pages → under "Build and deployment," set Source to "Deploy from a branch" and Branch to `gh-pages` (this branch doesn't exist yet — it gets created automatically the first time the workflow below runs).

4. **Push again (or just wait)** — the included GitHub Actions workflow (`.github/workflows/publish.yml`) automatically builds the Quarto site and deploys it to the `gh-pages` branch on every push to `main`. No local Quarto installation required for this to work.

5. Your site will be live at `https://<yourusername>.github.io/kali-website/` (or `https://<yourusername>.github.io/` if you named the repo that way).

## Editing locally (optional but recommended)

If you want to preview changes before pushing, install Quarto (https://quarto.org/docs/get-started/) and run:
```bash
quarto preview
```
from inside the project folder. This opens a live-reloading preview in your browser.

## What to fill in

- `index.qmd` — About text, contact links (Scholar/ORCID/Bluesky/Twitter/email), verify the institution table dates, adjust map pins/coordinates.
- `research.qmd` — one section per research theme (3–5 recommended), each with a paragraph + citation.
- `grants.qmd` — duplicate the `.flat-entry` block per grant, most recent first.
- `publications.qmd` — add entries under year headings, most recent year first.
- `media.qmd` — same flat-list pattern as grants.
- `posts/` — one folder per Updates entry. Duplicate `posts/2026-06-new-role/` for each new update; instructions are in that file.
- `_quarto.yml` — update `site-url` once you know your final GitHub Pages URL, and the email address in the navbar.
- `styles.scss` — the `$primary` accent colour is currently a muted forest green; change the hex code if you'd like a different accent.
