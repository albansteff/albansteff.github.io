# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

Personal portfolio/blog site for Alban Steff (Data Scientist), built with **Jekyll 4.x** and hosted on **GitHub Pages**. The repo doubles as the distribution package for the jekyll-theme-cayman gem (`jekyll-theme-cayman.gemspec`).

## Build & Dev Commands

```bash
# Install dependencies (once)
script/bootstrap        # runs: gem install bundler && bundle install

# Local dev server at http://localhost:4000
script/server           # runs: bundle exec jekyll serve

# Run HTML validation tests
script/cibuild
```

On Windows, these shell scripts require Git Bash or WSL.

## Architecture

### Rendering pipeline

Markdown files (`*.md`) → Jekyll → static HTML, served via GitHub Pages on push to `main`.

### Customizations over the base Cayman theme

- [_layouts/default.html](_layouts/default.html) — overrides the theme's default layout to inject a custom navigation bar (Home, Things I've Learned, Kaggle, LinkedIn, GitHub, DL/ML Books)
- [_includes/head-custom.html](_includes/head-custom.html) — adds MathJax for LaTeX math rendering in pages
- [assets/css/style.scss](assets/css/style.scss) — minimal CSS extending the theme

### Content pages

| File | URL | Purpose |
|------|-----|---------|
| [index.md](index.md) | `/` | Homepage / about |
| [blogposts.md](blogposts.md) | `/blogposts` | "Things I've Learned" links |
| [books.md](books.md) | `/books` | ML/DL book references |

### Configuration

[_config.yml](_config.yml) controls site title, description, theme, and social links (Kaggle, LinkedIn). Navigation links are hardcoded in `_layouts/default.html`, not driven by config.

## Deployment

Push to `main` → GitHub Pages auto-builds and deploys. No manual deploy step needed.
