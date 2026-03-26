# CLAUDE.md

## Project Overview

Academic homepage for **Arthur Stenzel** (Associate Professor of Financial Management, University of St.Gallen). Built with **Hugo** static site generator using the **Hugo Academic / Hugo Blox Builder** theme. Deployed to **Netlify** (primary) and **GitHub Pages** (secondary).

Live site: https://arthurstenzel-main.netlify.app/

## Tech Stack

- **Static site generator:** Hugo v0.124.1 (extended edition)
- **Theme:** Hugo Blox Builder v5.9.7 (Academic CV theme)
- **Module system:** Go modules (`go.mod`)
- **Styling:** SCSS (custom overrides in `assets/scss/custom.scss`)
- **Content format:** Markdown with YAML front matter
- **CI/CD:** GitHub Actions (`.github/workflows/`)
- **Deployment:** Netlify (main), GitHub Pages (backup)

## Directory Structure

```
config/_default/       # Hugo configuration (YAML): hugo.yaml, params.yaml, menus.yaml, languages.yaml, module.yaml
content/               # All site content (Markdown)
  _index.md            # Homepage — defines section order and widget configuration
  publication/         # Individual publication folders, each with index.md
  authors/admin/       # Author profile (Arthur Stenzel)
  slides/              # Presentation slides
layouts/               # Custom Hugo templates overriding the theme
  partials/blocks/     # Custom widgets: about.biography.html, collection.html, manfred.teaching.html
  partials/functions/  # Custom rendering logic
  partials/views/      # Display layout templates
assets/scss/           # Custom SCSS (custom.scss)
static/uploads/        # Static files (CV.pdf, resume.pdf)
data/themes/           # Theme color definitions (minimal.toml)
i18n/                  # Translation strings (en.yaml)
.github/workflows/     # CI/CD pipelines
```

## Build & Development

```bash
# Local development server
hugo server

# Production build
hugo --minify --baseURL "https://arthurstenzel-main.netlify.app/"
```

No `package.json` or npm — Hugo manages everything via Go modules.

## Key Configuration Files

| File | Purpose |
|------|---------|
| `config/_default/hugo.yaml` | Base URL, pagination, build settings |
| `config/_default/params.yaml` | Theme, fonts, SEO, features (search, analytics) |
| `config/_default/menus.yaml` | Navigation bar links and ordering (by weight) |
| `config/_default/module.yaml` | Hugo Blox module imports |
| `config/_default/languages.yaml` | Language settings (English only) |
| `data/themes/minimal.toml` | Color palette — primary is HSG green `#095f2d` |
| `go.mod` | Go module dependencies |

## Content Conventions

### Publications (`content/publication/`)

Each publication is a folder containing `index.md` with YAML front matter:

```yaml
title: "Paper Title"
authors:
  - Author One
  - admin            # References the site owner
date: "2024-01-01T00:00:00Z"
doi: "10.xxxx/xxxxx"
publication_types:
  - "Publication"     # Options: "Publication", "Working Paper", "Professional Publication"
publication: "Journal Name"
publication_short: "Abbrev."
abstract: "..."
tags: []
```

The homepage groups publications by `publication_types` into three sections: Publications, Working Papers, and Professional Publications.

**Automated import:** Pushing `publications.bib` to `main` triggers a GitHub Action that converts BibTeX to Markdown via `academic import` (Python `academic==0.10.0`) and creates a PR.

### Author Profile (`content/authors/admin/_index.md`)

Contains biography, role, organization, education, social links (Google Scholar, SSRN).

### Teaching Section

Configured as a custom widget (`manfred.teaching`) in `content/_index.md`. Course details are inline in the homepage front matter.

### Homepage (`content/_index.md`)

Single-page layout with ordered section blocks. Each block has:
- `block:` type (e.g., `about.biography`, `collection`, `manfred.teaching`, `contact`)
- `id:` used for anchor navigation (must match `menus.yaml` links)
- `content:` section-specific configuration

## Styling

- **Theme colors:** Defined in `data/themes/minimal.toml` — HSG green (`#095f2d`)
- **Custom SCSS:** `assets/scss/custom.scss` — reduced section padding, rectangular avatar, course list styling, responsive tweaks
- **Editor config:** 2-space indentation, UTF-8, LF line endings (`.editorconfig`)

## CI/CD Workflows

| Workflow | Trigger | Purpose |
|----------|---------|---------|
| `publish.yaml` | Push to `main` | Build with Hugo and deploy to GitHub Pages |
| `import-publications.yml` | Push `publications.bib` to `main` | Convert BibTeX to Markdown, open PR |

## Common Tasks

### Add a new publication
1. Create a new folder under `content/publication/` (folder name = short identifier)
2. Add `index.md` with the required YAML front matter fields
3. Or: add entry to `publications.bib` and let the GitHub Action generate it

### Update teaching courses
Edit the `manfred.teaching` block in `content/_index.md`.

### Update author bio
Edit `content/authors/admin/_index.md`.

### Update navigation
Edit `config/_default/menus.yaml` — items are ordered by `weight`.

### Update CV
Replace `static/uploads/CV.pdf`.

## Conventions for AI Assistants

- **Language:** Site content is in English; README.md is in German. Follow the existing language for each file.
- **Indentation:** 2 spaces for YAML, HTML, SCSS. See `.editorconfig`.
- **Line endings:** LF (Unix-style).
- **No trailing whitespace** except in Markdown files.
- **Hugo shortcodes and Go templates** are used in layouts — be careful with `{{ }}` syntax.
- **Do not modify** files under `go.mod` or `go.sum` directly — use `hugo mod` commands.
- **Theme overrides** go in `layouts/`, not by modifying the theme source.
- **Test changes locally** with `hugo server` before committing.
- **Publication types** must be one of: `"Publication"`, `"Working Paper"`, `"Professional Publication"` — these strings are used for filtering on the homepage.
