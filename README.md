# BonniciLABS

Personal portfolio — Jekyll, no theme, hosted on GitHub Pages.
Design: "Forensic Terminal".

## Structure

```
_config.yml          Site settings (title, email, callsign, url)
_data/projects.yml   ← edit this to add / change projects
_includes/           head, header, footer partials
_layouts/default.html  Page shell + hero hex-dump script
assets/css/main.scss   All styling (compiled to main.css by Jekyll)
index.html           Hero + evidence grid (loops over _data/projects.yml)
404.html             On-brand not-found page
CNAME                Custom domain (bonnicilabs.com)
```

## Adding a project

Open `_data/projects.yml` and copy a block:

```yaml
- ref: "NEW-06"
  title: "Project name"
  category: "APPLICATION"      # APPLICATION | RESEARCH | ARCHIVE | ...
  status: "IN DEVELOPMENT"
  state: "dev"                 # dev | live | ongoing | archive  → dot colour
  description: >-
    One short paragraph.
  tags: "tag · tag · tag"
  progress: 40                 # optional → shows completion meter
  progress_label: "BUILD"      # optional label next to the %
  meta_left: "key: value"      # small mono note, bottom-left of the card
  url: "https://github.com/..." # where "open file" points
  # featured: true             # optional → full-width card
```

No code changes needed — the homepage renders whatever is in this file.

## Run locally

```
bundle exec jekyll serve
```

(or just push to the `gh-pages` branch and let GitHub Pages build it)
