---
title: Contributing
permalink: /contributing/
layout: single
---
# Contributing a Project

Each team adds exactly two things:

1. One markdown file in `_projects/`
2. One poster image in `assets/images/posters/`

## Step 1: Add the poster image

- Export your poster as `.png`, `.jpg`, or `.svg`.
- Copy it into `assets/images/posters/`.
- Use a short, lowercase filename such as `riverwatch-dashboard.png`.

## Step 2: Add the project markdown file

- Copy `_projects/_TEMPLATE.md` to a new file such as `_projects/2026-spring-riverwatch-dashboard.md`.
- Fill in every required front matter field:
  - `title`
  - `semester`
  - `team`
  - `tags`
  - `repo_url`
  - `demo_url`
  - `poster_image`
  - `short_abstract`
- Change `published: false` to `published: true`, or remove the line once your page is ready to appear on the site.

## Step 3: Match the semester slug

The `semester` field must match an existing semester archive page.

Examples:

- `2025-fall`
- `2026-spring`

If a new semester does not exist yet, copy an existing semester folder like `2026-spring/`, rename it, and update the front matter:

- `title`
- `semester`
- `semester_order`
- `description`
- `permalink`

## Step 4: Preview locally

From the repo root:

```bash
bundle install
bundle exec jekyll serve
```

Then open the local address shown in the terminal and verify:

- your project appears on the home page,
- it appears on the correct semester archive page,
- the poster image loads,
- the repo/demo links work.

