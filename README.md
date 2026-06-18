# BonniciLABS

Personal portfolio — Jekyll, no theme, hosted on GitHub Pages.
Design: "Forensic Terminal".

## Structure

```
_config.yml            Site settings + projects collection
_projects/             ← one file per project (its own page lives here)
_layouts/default.html  Page shell (header, footer, hero hex script)
_layouts/project.html  Project "case file" detail page
_includes/             head / header / footer partials
assets/css/main.scss   All styling (compiled to main.css by Jekyll)
index.html             Hero + evidence grid + archive (reads _projects)
404.html               On-brand not-found page
CNAME                  Custom domain (bonnicilabs.com)
```

Each project in `_projects/` automatically gets:
- a card on the homepage (active projects in **Evidence**, archived ones in **Archive**), and
- its own detail page at `/projects/<filename>/`.

## Adding a project

Create `_projects/my-project.md`:

```yaml
---
title: My Project
ref: NEW-06
category: APPLICATION        # APPLICATION | RESEARCH | ROBOT | ...
status: IN DEVELOPMENT
state: dev                   # dev | live | ongoing | archive  → dot colour
order: 5                     # controls position (lower = earlier)
summary: One line for the homepage card.
tags: tag · tag · tag
# --- optional ---
featured: true               # full-width card on the homepage
progress: 40                 # shows a completion meter (+ progress_label)
progress_label: BUILD
stack: [Swift, SQLite]       # shown in the detail-page spec strip
platform: macOS · iOS
year: 2026
meta_left: "key: value"      # small mono note on the card
repo: https://github.com/... # adds a "→ repository" link
archived: true               # moves it to the Archive section
---

## A heading

Markdown body for the detail page goes here.
```

The homepage and detail page both build themselves from this — no template edits needed.

## Run locally

```
bundle exec jekyll serve
```

…or just push to the `gh-pages` branch and let GitHub Pages build it.
