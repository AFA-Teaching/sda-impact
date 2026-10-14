# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Educational portal for the "Impact Data Scientist" module at Sorbonne Data Analytics. Static site built with MkDocs Material, entirely in French.

Live site: https://afa-teaching.github.io/sda-impact/

## Commands

```bash
# Install dependency
pip install mkdocs-material

# Local dev server (http://localhost:8000)
mkdocs serve

# Build static site (output in site/)
mkdocs build
```

Deployment is automatic via GitHub Actions on push to `main` — no manual deploy needed.

## Architecture

- **`mkdocs.yml`** — Site configuration: navigation structure, theme settings, markdown extensions, plugins
- **`docs/`** — All site content (68 markdown files)
  - `index.md` — Homepage
  - `sessions/01-productivite-ia/` — Session 1: AI Productivity (18 files)
  - `sessions/02-data-storytelling/` — Session 2: Data Storytelling (22 files)
  - `sessions/03-gestion-produit/` — Session 3: Product Management (23 files)
  - `sessions/04-travaux-pratiques/` — Session 4: Practical Work (3 files)
  - `assets/images/` — 65 PNG infographics with descriptive filenames
  - `stylesheets/extra.css` — Custom CSS (video embed styling)
- **`site/`** — Generated output (gitignored, do not edit)

Each session folder has an `index.md` entry point. Navigation hierarchy is defined in `mkdocs.yml` under `nav:`.

## Content Conventions

- All content is written in **French**
- Markdown extensions available: admonitions, collapsible details, tabbed content, emoji (twemoji), attr_list, md_in_html
- Infographic images follow descriptive naming: `docs/assets/images/<descriptive-name>.png`
- External resources link to YouTube, FigJam boards, Google Slides, and Google Docs
- Theme: Material for MkDocs with deep purple primary / amber accent, dark mode toggle
